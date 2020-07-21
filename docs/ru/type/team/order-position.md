Тип `Cubux.OrderPosition`
=========================

Позиция заказа.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`       | UUID
`order_uuid`    | `uuid`, NULL | Обязательно. UUID заказа [`Cubux.Order`][Cubux.Order].
`category_uuid` | `uuid`, NULL | Обязательно. UUID категории доходов [`Cubux.SelfCategory`][Cubux.SelfCategory].
`price`         | `float`      | Обязательно. Цена единицы продукта/услуги
`quantity`      | `float`      | Обязательно. Количество продукта/услуги
`sort`          | `uint16`     | Порядок сортировки


[Cubux.Order]: ./order.md
[Cubux.SelfCategory]: ./category.md
