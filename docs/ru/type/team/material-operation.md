Тип `Cubux.MaterialOperation`
=============================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за оборот по
материалам на складе.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`material_uuid` | `uuid` | Обязательно. UUID материала [`Cubux.MaterialSource`][Cubux.MaterialSource].
`unit_uuid` | `uuid` | Обязательно. UUID единицы измерения [`Cubux.MeasureUnit`][Cubux.MeasureUnit].
`quantity` | `float` | Обязательно. Количество. Минимум `1e-10`.

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

**Важно**: Используемая единица измерения не должна быть связана с иным
материалом. Т.е. можно использовать общие единицы измерения, не привязанные ни к
каким материалам, и единицы, привязанные к указанному материалу.

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.MaterialSource]: ./material-source.md
[Cubux.MeasureUnit]: ./measure-unit.md