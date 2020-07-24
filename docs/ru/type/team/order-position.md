Тип `Cubux.OrderPosition`
=========================

> УДАЛЁН

Позиция заказа.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`   | UUID
`order_uuid`    | `uuid`   | Обязательно. UUID заказа [`Cubux.Order`][Cubux.Order].
`category_uuid` | `uuid`   | Обязательно. UUID категории доходов [`Cubux.SelfCategory`][Cubux.SelfCategory].
`price`         | `float`  | Обязательно. Цена единицы продукта/услуги
`quantity`      | `float`  | Обязательно. Количество продукта/услуги
`sort`          | `uint16` | Порядок сортировки


[Cubux.Order]: ./order.md
[Cubux.SelfCategory]: ./category.md
