Тип `Cubux.ProductAddSpecification`
===================================

Дополнительная затрата в структуре продукта [`Cubux.Product`][Cubux.Product] в
виде тех.карты.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`parent_product_hash`** PK | `md5` | Хеш продукта, к которому добавлено
**`specification_uuid`** PK | `uuid` | UUID тех.карты [`Cubux.Specification`][Cubux.Specification]
`quantity` | `string` | Количество. Строка, содержащая дробное число максимум с 10 знаками.

**Важно**: Количество в `quantity` передаётся в виде строки, а не числа, для
того, чтобы избежать возможных потерь точности при вычислении хеша продукт.


[Cubux.Product]: ./product.md
[Cubux.Specification]: ./specification.md
