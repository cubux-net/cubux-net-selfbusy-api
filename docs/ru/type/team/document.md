Тип `Cubux.Document`
====================

Документ, в соответствии с которым проводятся изменения данных, подлежащих
учёту (остатки на счетах, материалы на складе, заказы и т.п.).

Документ объединяет собой ряд различных операций, которые могут быть проведены
только одновременно. Например, при покупке материала операции списания средств
со счёта и соответствующее поступления материала на склад.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | Обязательно. UUID используется в других объектах операций, относящихся к данному документу.
`type` | `string` | Обязательно. Тип документа определяет набор операций. Значения см. ниже.
`datetime` | `datetime` | Дата и время
`project_uuid`  | `uuid`, NULL | UUID проекта [`Cubux.SelfProject`][Cubux.SelfProject].
`comment` | `string` | Комментарий. Максимум 4000 символов.

**Важно**: Изменение отдельных операций (частей документа) невозможно. Для
достижения результата необходимо выполнять удаление старого документа и создание
нового с изменёнными данными.

### Типы операций `type`

Ниже в подзаголовках перечислены возможные значения для поля `type` вместе с
описанием необходимых операций. В скобках после имени типа указан внутренний
номер транзакции.

#### `fabricate_to_store` (8)

Изготовление продукции вне заказа на склад готовой продукции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `1` - out | 0..n | Расход материалов со склада
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `0` - in | 1 | Поступление продукта на склад

#### `general_expense` (1)

Прочие расходы, кроме заказов и покупки материалов на склад.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `1` - out | 1 | Списание средств со счёта
[`Cubux.SelfCategoryOperation`][Cubux.SelfCategoryOperation] | `0` - in | 1 | Категория расходов (тип `expense`)

#### `general_income` (3)

Продажа продукта вне заказа без склада готовой продукции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | `0` - in | 1 | Оборот продукта
[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | `1` - out | 1 | Оборот продукта
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `1` - out | 0..n | Расход материалов со склада
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `0` - in | 1 | Поступление средств на счёт

#### `initial_expense` (20a)

Начальный остаток-расход.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `1` - out | 1 | Списание средств со счёта

#### `initial_income` (20)

Начальный остаток-приход.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `0` - in | 1 | Поступление средств на счёт

#### `material_buy` (2)

Приобретение одного материала на склад посредством списания средств с одного
счета.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `0` - in | 1 | Добавление материала на склад
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `1` - out | 1 | Списание средств со счёта

#### `material_dispose` (14)

Списание материала со склада. Является убытком. Не путать с отменой покупки.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `1` - out | 1 | Списание материала со склада

#### `order_add_service` (7)

Включение в заказ услуги.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `0` - in | 1 | Добавление услуги в заказ
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `1` - out | 1 | Списание средств со счёта

#### `order_add_stored_product` (10)

Включение в заказ готовой продукции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `0` - in | 1 | Добавление продукта в заказ
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `1` - out | 1 | Списание продукта со склада

#### `order_create` (4)

Регистрация позиции в заказе.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderPayOperation`][Cubux.OrderPayOperation] | `0` - in | 1 | Увеличение долга заказчика за заказ
[`Cubux.OrderSellOperation`][Cubux.OrderSellOperation] | `1` - out | 1 | Обязательство обеспечить продукт для заказа

#### `order_dispose_product` (11)

Списание готового продукта из заказа.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `1` - out | 1 | Списание продукта из заказа

#### `order_income` (5)

Поступление дохода за заказ.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderPayOperation`][Cubux.OrderPayOperation] | `1` - out | 1 | Уменьшение долга заказчика за заказ
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `0` - in | 1 | Поступление средств на счёт

#### `order_product_close` (6)

Закрытие заказа по позиции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | `0` - in | 1 | Оборот продукта
[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | `1` - out | 1 | Оборот продукта
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `1` - out | 1 | Списание продукта из заказа
[`Cubux.OrderSellOperation`][Cubux.OrderSellOperation] | `0` - in | 1 | Исполнение обязательства обеспечить продукт для заказа

#### `order_product_fabricate` (19)

Изготовление продукта в заказе.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `0` - in | 1 | Добавление продукта в заказ
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `1` - out | 0..n | Расход материалов со склада

#### `order_product_to_store` (12)

Отправка готовой продукции из заказа на склад.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `1` - out | 1 | Списание продукта из заказа
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `0` - in | 1 | Добавление продукта на склад

#### `return_stored_to_material` (21)

Изготовление продукции вне заказа на склад готовой продукции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `0` - in | 0..n | Возврат материалов на склада
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `1` - out | 1 | Отмена создания продукта на складе

#### `stored_product_dispose` (13)

Списание готового продукта со склада готовой продукции

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `1` - out | 1 | Списание продукта со склада

#### `stored_product_sell` (9)

Продажа продукта вне заказа со склада готовой продукции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | `0` - in | 1 | Оборот продукта
[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | `1` - out | 1 | Оборот продукта
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `0` - in | 1 | Поступление средств на счёт
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `1` - out | 1 | Списание продукта со склада


[Cubux.CapitalOperation]: ./capital-operation.md
[Cubux.MaterialOperation]: ./material-operation.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.OrderPayOperation]: ./order-pay-operation.md
[Cubux.OrderProductOperation]: ./order-product-operation.md
[Cubux.OrderSellOperation]: ./order-sell-operation.md
[Cubux.ProductOperation]: ./product-operation.md
[Cubux.SelfAccountOperation]: ./account-operation.md
[Cubux.SelfCategoryOperation]: ./category-operation.md
[Cubux.SelfProject]: ./project.md
