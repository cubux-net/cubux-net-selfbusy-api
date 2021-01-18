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
`capital_operation` | `Array:`[`Cubux.CapitalOperation`][Cubux.CapitalOperation] | Операции по уставному капиталу
`category` | `Array:`[`Cubux.SelfCategory`][Cubux.SelfCategory] | Справочник категорий
`category_link` | `Array:`[`Cubux.SelfCategoryLink`][Cubux.SelfCategoryLink] | Связи между категориями
`category_operation` | `Array:`[`Cubux.SelfCategoryOperation`][Cubux.SelfCategoryOperation] | Операции по категориям
`category_operation_link` | `Array:`[`Cubux.SelfCategoryOperationLink`][Cubux.SelfCategoryOperationLink] | Связи между расходами по категориям и доходными категориями
`category_specification` | `Array:`[`Cubux.SelfCategorySpecification`][Cubux.SelfCategorySpecification] | Связи категорий с тех.картами
`customer` | `Array:`[`Cubux.Customer`][Cubux.Customer] | Справочник заказчиков
`document` | `Array:`[`Cubux.Document`][Cubux.Document] | Документы
`images` | `Array:`[`Cubux.Image`][Cubux.Image] | Изображения
`material_operation` | `Array:`[`Cubux.MaterialOperation`][Cubux.MaterialOperation] | Операции по материалам на складе
`material_source` | `Array:`[`Cubux.MaterialSource`][Cubux.MaterialSource] | Справочник материалов (неисчисляемые ресурсы, как таковые)
`measure_unit` | `Array:`[`Cubux.MeasureUnit`][Cubux.MeasureUnit] | Единицы измерения
`order` | `Array:`[`Cubux.Order`][Cubux.Order] | Заказы
`order_pay_operation` | `Array:`[`Cubux.OrderPayOperation`][Cubux.OrderPayOperation] | Операции по оплате в заказе
`order_position` _(удалён)_ | `Array:`[`Cubux.OrderPosition`][Cubux.OrderPosition] | Позиции заказов
`order_product_operation` | `Array:`[`Cubux.OrderProductOperation`][Cubux.OrderProductOperation] | Операции по продуктам и услугам в заказе
`order_sell_operation` | `Array:`[`Cubux.OrderSellOperation`][Cubux.OrderSellOperation] | Операции по позициям в заказе
`product` | `Array:`[`Cubux.Product`][Cubux.Product] | Описание структуры продуктов **\*1)**
`product_add_material` | `Array:`[`Cubux.ProductAddMaterial`][Cubux.ProductAddMaterial] | Дополнительные затраты материалов в структуре продуктов **\*1)**
`product_add_product` | `Array:`[`Cubux.ProductAddProduct`][Cubux.ProductAddProduct] | Дополнительные затраты иных продуктов в структуре продуктов **\*1)**
`product_add_specification` | `Array:`[`Cubux.ProductAddSpecification`][Cubux.ProductAddSpecification] | Дополнительные затраты тех.карт в структуре продуктов **\*1)**
`product_operation` | `Array:`[`Cubux.ProductOperation`][Cubux.ProductOperation] | Операции по продуктам на складе
`project` | `Array:`[`Cubux.SelfProject`][Cubux.SelfProject] | Справочник проектов
`settings` | [`Cubux.SelfSettings`][Cubux.SelfSettings] | Настройки
`specification` | `Array:`[`Cubux.Specification`][Cubux.Specification] | Техкарты
`specification_ingredient` | `Array:`[`Cubux.SpecificationIngredient`][Cubux.SpecificationIngredient] | Ингредиенты техкарт

**\*1)**: Справочник структуры продуктов представляет собой динамический
справочник:

*   Каждый раз в нём обязательно передаются описания всех продуктов, упомянутых
    где-либо именно в этом же пакете данных: как при получении данных с сервера,
    так и при отправке данных на сервер.
*   Удаление данных из этого справочника не передаётся через синхронизацию.
    Клиенту следует самостоятельно вычищать из этого справочника продукты,
    неиспользуемые у него локально, в произвольное время.
*   Клиент _может_ отправлять на сервер неиспользуемые описания продуктов.
    Сервер будет их игнорировать, добавляя в ошибки тикета сообщения уровня
    `dev_notice`.


[Cubux.CapitalOperation]: ../team/capital-operation.md
[Cubux.Customer]: ../team/customer.md
[Cubux.Document]: ../team/document.md
[Cubux.Image]: ../team/image.md
[Cubux.MaterialOperation]: ../team/material-operation.md
[Cubux.MaterialSource]: ../team/material-source.md
[Cubux.MeasureUnit]: ../team/measure-unit.md
[Cubux.Order]: ../team/order.md
[Cubux.OrderPayOperation]: ../team/order-pay-operation.md
[Cubux.OrderPosition]: ../team/order-position.md
[Cubux.OrderProductOperation]: ../team/order-product-operation.md
[Cubux.OrderSellOperation]: ../team/order-sell-operation.md
[Cubux.Product]: ../team/product.md
[Cubux.ProductAddMaterial]: ../team/product-add-material.md
[Cubux.ProductAddProduct]: ../team/product-add-product.md
[Cubux.ProductAddSpecification]: ../team/product-add-specification.md
[Cubux.ProductOperation]: ../team/product-operation.md
[Cubux.SelfAccount]: ../team/account.md
[Cubux.SelfAccountOperation]: ../team/account-operation.md
[Cubux.SelfCategory]: ../team/category.md
[Cubux.SelfCategoryLink]: ../team/category-link.md
[Cubux.SelfCategoryOperation]: ../team/category-operation.md
[Cubux.SelfCategoryOperationLink]: ../team/category-operation-link.md
[Cubux.SelfCategorySpecification]: ../team/category-specification.md
[Cubux.SelfProject]: ../team/project.md
[Cubux.SelfSettings]: ../team/settings.md
[Cubux.Specification]: ../team/specification.md
[Cubux.SpecificationIngredient]: ../team/specification-ingredient.md
