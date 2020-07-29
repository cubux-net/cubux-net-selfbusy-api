Тип `Cubux.OrderSellOperation`
=================================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за позицию
продукта или услуги в заказе (бухгалтерский счёт 90).

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`amount` | `float` | Обязательно. Сумма. Минимум `0.01`.
`order_uuid` | `uuid` | Обязательно. UUID заказа [`Cubux.Order`][Cubux.Order].
`category_uuid` | `uuid` | Обязательно. UUID категории [`Cubux.SelfCategory`][Cubux.SelfCategory].
`quantity` | `float` | Обязательно. Количество. Минимум `1e-10`.

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

**Важно**: Категория должна доходной (`type` = `"income"`).

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.Order]: ./order.md
[Cubux.SelfCategory]: ./category.md
