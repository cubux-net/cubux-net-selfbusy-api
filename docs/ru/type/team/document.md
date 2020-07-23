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
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `1` - out | 1..n | Расход материалов со склада
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `0` - in | 1 | Поступление продукта на склад

#### `general_expense` (1)

Прочие расходы, кроме заказов и покупки материалов на склад.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `1` - out | 1 | Списание средств со счёта
[`Cubux.SelfCategoryOperation`][Cubux.SelfCategoryOperation] | `0` - in | 1 | Категория расходов (тип `expense`)

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

#### `stored_product_dispose` (13)

Списание готового продукта со склада готовой продукции

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `1` - out | 1 | Списание продукта со склада

#### `order_product_fabricate` (19)

Изготовление продукта в заказе.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | `0` - in | 1 | Добавление продукта в заказ
[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | `1` - out | 1..n | Расход материалов со склада

#### `stored_product_sell` (9)

Продажа продукта вне заказа со склада готовой продукции.

Операция | Направление | Кол-во | Описание
-------- | ----------- | ------ | --------
[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | `0` - in | 1 | Поступление средств на счёт
[`Cubux.ProductOperation`][Cubux.ProductOperation] | `1` - out | 1 | Списание продукта со склада


[Cubux.MaterialOperation]: ./material-operation.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.OrderProductOperation]: ./order-product-operation.md
[Cubux.ProductOperation]: ./product-operation.md
[Cubux.SelfAccountOperation]: ./account-operation.md
[Cubux.SelfCategoryOperation]: ./category-operation.md
