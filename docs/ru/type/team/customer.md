Тип `Cubux.Customer`
====================

Заказчик.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`    | UUID
`name`        | `string`  | Обязательно. Название. Максимум 255 символов.
`phone`       | `string`  | Телефон. Максимум 64 символов.
`email`       | `string`  | E-mail. Максимум 128 символов.
`address`     | `string`  | Адрес. Максимум 1000 символов.
`comment`     | `string`  | Комментарий. Максимум 1000 символов.
`is_hidden`   | `boolean` | Является ли скрытым
`icon_uuid`   | `uuid`, NULL | UUID изображения [`Cubux.Image`][Cubux.Image] с `purpose` = `"customer"` и `size_type` = `"icon"`
`icon_name`   | `string`  | Необязательно. Имя предопределённой иконки. Максимум 32 символа.


[Cubux.Image]: ./image.md
