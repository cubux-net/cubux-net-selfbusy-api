Тип `Cubux.Selfbusy.TeamData`
=========================

Словарь объектов для контекста данных команды.

Используется в:

*   `Cubux.Sync.Data`
*   `Cubux.Sync.DataDiff`
*   `Cubux.Sync.DataPatch`

Объекты в `objects`:

Поле | Тип | Описание
---- | --- | --------
`account` | `Array:`[`Cubux.SelfAccount`][Cubux.SelfAccount] | Справочник счетов
`category` | `Array:`[`Cubux.SelfCategory`][Cubux.SelfCategory] | Справочник категорий
`category_link` | `Array:`[`Cubux.SelfCategoryLink`][Cubux.SelfCategoryLink] | Связи между категориями
`customer` | `Array:`[`Cubux.Customer`][Cubux.Customer] | Справочник заказчиков
`material_source` | `Array:`[`Cubux.MaterialSource`][Cubux.MaterialSource] | Справочник материалов (неисчисляемые ресурсы, как таковые)
`measure_unit` | `Array:`[`Cubux.MeasureUnit`][Cubux.MeasureUnit] | Единицы измерения
`project` | `Array:`[`Cubux.SelfProject`][Cubux.SelfProject] | Справочник проектов
`specification` | `Array:`[`Cubux.Specification`][Cubux.Specification] | Техкарты
`specification_ingredient` | `Array:`[`Cubux.SpecificationIngredient`][Cubux.SpecificationIngredient] | Ингредиенты техкарт


[Cubux.Customer]: ../team/customer.md
[Cubux.MaterialSource]: ../team/material-source.md
[Cubux.MeasureUnit]: ../team/measure-unit.md
[Cubux.SelfAccount]: ../team/account.md
[Cubux.SelfCategory]: ../team/category.md
[Cubux.SelfCategoryLink]: ../team/category-link.md
[Cubux.SelfProject]: ../team/project.md
[Cubux.Specification]: ../team/specification.md
[Cubux.SpecificationIngredient]: ../team/specification-ingredient.md
