Тип `Cubux.Order`
=================

Заказ.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`     | UUID
`title`         | `string`   | Обязательно. Название. Максимум 128 символов.
`customer_uuid` | `uuid`, NULL | UUID заказчика [`Cubux.Customer`][Cubux.Customer].
`project_uuid`  | `uuid`, NULL | UUID проекта [`Cubux.SelfProject`][Cubux.SelfProject].
`created_at`    | `datetime` | Дата и время


[Cubux.Customer]: ./customer.md
[Cubux.SelfProject]: ./project.md
