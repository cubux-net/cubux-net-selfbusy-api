Тип `Cubux.SelfCategoryOperation`
================================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за связь с
категорией (бухгалтерский счёт 26).

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`category_uuid` | `uuid` | Обязательно. UUID категории [`Cubux.SelfCategory`][Cubux.SelfCategory].

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

**Важно**: Тип категории зависит от типа документа, к которому относится
операция.

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.SelfCategory]: ./category.md
