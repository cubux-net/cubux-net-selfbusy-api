Тип `Cubux.SpecificationGroup`
===================================

Группа для ингредиентов [`Cubux.SpecificationIngredient`][Cubux.SpecificationIngredient]
техкарты [`Cubux.Specification`][Cubux.Specification].

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`    | UUID
`specification_uuid` | `uuid` | Обязательно. UUID техкарты [`Cubux.Specification`][Cubux.Specification], которой принадлежит.
`name`        | `string` | Обязательно. Название. Максимум 128 символов.
`comment`     | `string` | Комментарий. Максимум 8000 символов.
`sort`        | `uint16` | Порядок сортировки

*   **Важно:** Поле `specification_uuid` может быть лишь назначено при создании.
    Дальнейшее изменение запрещено - вместо этого следует использовать создание
    нового и удаление старого объектов.


[Cubux.MaterialSource]: ./material-source.md
[Cubux.MeasureUnit]: ./measure-unit.md
[Cubux.Specification]: ./specification.md
[Cubux.SpecificationIngredient]: ./specification-ingredient.md
