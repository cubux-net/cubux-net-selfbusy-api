Тип `Cubux.SelfAccount`
=======================

Счёт.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`    | UUID
`name`        | `string`  | Обязательно. Название. Максимум 255 символов.
`sort`        | `uint16`  | Порядок сортировки
`is_hidden`   | `boolean` | Является ли скрытым
`icon_uuid`   | `uuid`, NULL | UUID изображения [`Cubux.Image`][Cubux.Image] с `purpose` = `"self_account"` и `size_type` = `"icon"`


[Cubux.Image]: ./image.md
