Тип `Cubux.ProductOperation`
============================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за продукт на
складе (бухгалтерский счёт 40).

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`amount` | `float` | Обязательно. Сумма. Минимум `0.01`.
`category_uuid` | `uuid`, NULL | UUID категории [`Cubux.SelfCategory`][Cubux.SelfCategory].
`product_hash` | `md5`, NULL | Ссылка на описание структуры продукта [`Cubux.Product`][Cubux.Product]
`quantity` | `float` | Обязательно. Минимум `1e-10`.

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

**Важно**: Категория должна доходной (`type` = `"income"`).

**Важно**: Категория `category_uuid` и продукт `product_hash` не могут быть NULL
вместе.

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.Product]: ./product.md
[Cubux.SelfCategory]: ./category.md
