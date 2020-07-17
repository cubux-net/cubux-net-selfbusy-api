Тип `Cubux.Order`
=================

Заказ.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK   | `uuid`     | UUID
`title`         | `string`   | Обязательно. Название. Максимум 128 символов.
`customer_uuid` | `uuid`     | Обязательно. UUID заказчика [`Cubux.Customer`][Cubux.Customer].
`project_uuid` | `uuid`, NULL | UUID проекта [`Cubux.SelfProject`][Cubux.SelfProject].
`created_at`    | `datetime` | Дата и время

**Важно**: Заказчик `customer_uuid` может быть назначен только при создании и не
может быть изменён в дальнейшем.


[Cubux.Customer]: ./customer.md
[Cubux.SelfProject]: ./project.md
