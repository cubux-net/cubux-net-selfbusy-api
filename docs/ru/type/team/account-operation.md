Тип `Cubux.SelfAccountOperation`
================================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за оборот средств
на счету.

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`account_uuid` | `uuid` | Обязательно. UUID счёта [`Cubux.SelfAccount`][Cubux.SelfAccount].
`amount` | `float` | Обязательно. Количество. Минимум `0.01`.

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.SelfAccount]: ./account.md
