Тип `Cubux.ProductAddCategory`
==============================

Дополнительная затрата в структуре продукта [`Cubux.Product`][Cubux.Product] в
виде категории.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`parent_product_hash`** PK | `md5` | Хеш продукта, к которому добавлено
**`category_uuid`** PK | `uuid` | UUID категории [`Cubux.SelfCategory`][Cubux.SelfCategory]
`quantity` | `string` | Количество. Строка, содержащая дробное число максимум с 10 знаками.

**Важно**: Количество в `quantity` передаётся в виде строки, а не числа, для
того, чтобы избежать возможных потерь точности при вычислении хеша продукт.


[Cubux.Product]: ./product.md
[Cubux.SelfCategory]: ./category.md
