Тип `Cubux.SelfCategory`
=======================

Категория доходов/расходов.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`    | UUID
`type` | `enum("income", "expense")` | Обязательно. Тип категории. `"income"` - дохода, `"expense"` - расходы
`name`        | `string`  | Обязательно. Название. Максимум 255 символов.
`specification_uuid` | `uuid`, NULL | Связь с техкартой [`Cubux.Specification`][Cubux.Specification].
`cost`    | `decimal(.2)` | Стоимость товара по умолчанию при создании транзакции с этой категорией.
`is_service`  | `boolean` | Описывает ли категория услугу.
`sort`        | `uint16`  | Порядок сортировки.
`is_hidden`   | `boolean` | Является ли скрытой.

*   Связь с техкартой `specification_uuid` обязательна для доходной категории
    (`type` есть `"income"`), описывающей товар (`is_service` есть `false`).
    В остальных случаях поле сбрасывается в `null`.
*   Поля `cost` и `is_service` имеют смысл только для расходных категорий (`type` есть
    `"income"`).

[Cubux.Specification]: ./specification.md