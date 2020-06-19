Тип `Cubux.SpecificationIngredient`
===================================

Один из ингредиентов техкарты [`Cubux.Specification`][Cubux.Specification].

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK | `uuid`    | UUID
`specification_uuid` | `uuid` | Обязательно. UUID техкарты [`Cubux.Specification`][Cubux.Specification], которой принадлежит.
`source_uuid` | `uuid` | Обязательно. UUID материала [`Cubux.MaterialSource`][Cubux.MaterialSource].
`unit_uuid` | `uuid` | Обязательно. UUID единицы измерения [`Cubux.MeasureUnit`][Cubux.MeasureUnit].
`quantity` | `decimal(.10)` | Обязательно. Минимум `1e-10`.
`sort`        | `uint16`  | Порядок сортировки

*   **Важно:** Поле `specification_uuid` может быть лишь назначено при создании.
    Дальнейшее изменение запрещено - вместо этого следует использовать создание
    нового и удаление старого объектов.


[Cubux.MaterialSource]: ./material-source.md
[Cubux.MeasureUnit]: ./measure-unit.md
[Cubux.Specification]: ./specification.md
