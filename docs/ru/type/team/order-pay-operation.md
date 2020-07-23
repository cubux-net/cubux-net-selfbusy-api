Тип `Cubux.OrderPayOperation`
=================================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за расчёт по
заказам (бухгалтерский счёт 62).

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`order_uuid` | `uuid` | Обязательно. UUID заказа [`Cubux.Order`][Cubux.Order].
`amount` | `float` | Обязательно. Сумма. Минимум `0.01`.

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.Order]: ./order.md
