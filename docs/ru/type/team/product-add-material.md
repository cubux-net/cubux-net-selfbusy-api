Тип `Cubux.ProductAddMaterial`
===================

Дополнительная затрата в структуре продукта [`Cubux.Product`][Cubux.Product] в
виде материала.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`parent_product_hash`** PK | `md5` | Хеш продукта, к которому добавлено
**`material_uuid`** PK | `uuid` | UUID материала [`Cubux.MaterialSource`][Cubux.MaterialSource]
**`unit_uuid`** PK | `uuid` | UUID единицы измерения [`Cubux.MeasureUnit`][Cubux.MeasureUnit]
`quantity` | `string` | Количество. Строка, содержащая дробное число максимум с 10 знаками.

**Важно**: Количество в `quantity` передаётся в виде строки, а не числа, для
того, чтобы избежать возможных потерь точности при вычислении хеша продукт.


[Cubux.MaterialSource]: ./material-source.md
[Cubux.MeasureUnit]: ./measure-unit.md
[Cubux.Product]: ./product.md
