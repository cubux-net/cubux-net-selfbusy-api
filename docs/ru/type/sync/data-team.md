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
`account_operation` | `Array:`[`Cubux.SelfAccountOperation`][Cubux.SelfAccountOperation] | Операции по счетам
`category` | `Array:`[`Cubux.SelfCategory`][Cubux.SelfCategory] | Справочник категорий
`category_link` | `Array:`[`Cubux.SelfCategoryLink`][Cubux.SelfCategoryLink] | Связи между категориями
`category_operation` | `Array:`[`Cubux.SelfCategoryOperation`][Cubux.SelfCategoryOperation] | Операции по категориям
`customer` | `Array:`[`Cubux.Customer`][Cubux.Customer] | Справочник заказчиков
`document` | `Array:`[`Cubux.Document`][Cubux.Document] | Документы
`material_operation` | `Array:`[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | Операции по материалам на складе
`material_source` | `Array:`[`Cubux.MaterialSource`][Cubux.MaterialSource] | Справочник материалов (неисчисляемые ресурсы, как таковые)
`measure_unit` | `Array:`[`Cubux.MeasureUnit`][Cubux.MeasureUnit] | Единицы измерения
`order` | `Array:`[`Cubux.Order`][Cubux.Order] | Заказы
`order_pay_operation` | `Array:`[`Cubux.OrderPayOperation`][Cubux.OrderPayOperation] | Операции по оплате в заказе
`order_position` _(удалён)_ | `Array:`[`Cubux.OrderPosition`][Cubux.OrderPosition] | Позиции заказов
`order_product_operation` | `Array:`[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | Операции по продуктам и услугам в заказе
`order_sell_operation` | `Array:`[`Cubux.OrderSellOperation`][Cubux.OrderSellOperation] | Операции по позициям в заказе
`product_operation` | `Array:`[`Cubux.ProductOperation`][Cubux.ProductOperation] | Операции по продуктам на складе
`project` | `Array:`[`Cubux.SelfProject`][Cubux.SelfProject] | Справочник проектов
`specification` | `Array:`[`Cubux.Specification`][Cubux.Specification] | Техкарты
`specification_ingredient` | `Array:`[`Cubux.SpecificationIngredient`][Cubux.SpecificationIngredient] | Ингредиенты техкарт


[Cubux.Customer]: ../team/customer.md
[Cubux.Document]: ../team/document.md
[Cubux.MaterialOperation]: ../team/material-operation.md
[Cubux.MaterialSource]: ../team/material-source.md
[Cubux.MeasureUnit]: ../team/measure-unit.md
[Cubux.Order]: ../team/order.md
[Cubux.OrderPayOperation]: ../team/order-pay-operation.md
[Cubux.OrderPosition]: ../team/order-position.md
[Cubux.OrderProductOperation]: ../team/order-product-operation.md
[Cubux.OrderSellOperation]: ../team/order-sell-operation.md
[Cubux.ProductOperation]: ../team/product-operation.md
[Cubux.SelfAccount]: ../team/account.md
[Cubux.SelfAccountOperation]: ../team/account-operation.md
[Cubux.SelfCategory]: ../team/category.md
[Cubux.SelfCategoryLink]: ../team/category-link.md
[Cubux.SelfCategoryOperation]: ../team/category-operation.md
[Cubux.SelfProject]: ../team/project.md
[Cubux.Specification]: ../team/specification.md
[Cubux.SpecificationIngredient]: ../team/specification-ingredient.md
