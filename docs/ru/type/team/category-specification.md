Тип `Cubux.SelfCategorySpecification`
=====================================

Связь категории с тех.картой.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`uuid`** PK        | `uuid` | UUID
`category_uuid`      | `uuid` | Связь с категорией [`Cubux.SelfCategory`][Cubux.SelfCategory].
`specification_uuid` | `uuid` | Связь с техкартой [`Cubux.Specification`][Cubux.Specification].
`quantity`          | `float` | Количество. По умолчанию `1`. Минимум `0.001`.

[Cubux.SelfCategory]: ./category.md
[Cubux.Specification]: ./specification.md
