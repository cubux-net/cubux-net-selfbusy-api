Тип `Cubux.SelfAccountOperation`
================================

Часть документа [`Cubux.Document`][Cubux.Document], отвечающая за оборот средств
на счету (бухгалтерский счёт 51).

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
`uuid` **PK** | `uuid` | UUID операции.
`doc_uuid` | `uuid` | Обязательно. UUID документа, к которому относится.
`side` | [`Cubux.OperationSide`][Cubux.OperationSide] | Обязательно. Направление операции.
`amount` | `float` | Обязательно. Сумма. Минимум `0`.
`account_uuid` | `uuid` | Обязательно. UUID счёта [`Cubux.SelfAccount`][Cubux.SelfAccount].

**Важно**: Объекты данного типа должны обрабатываться только вместе с
соответствующим документом. Прямое изменение и удаление невозможно.

> TODO: Вероятно, придётся добавить тип операции.


[Cubux.Document]: ./document.md
[Cubux.OperationSide]: ./operation-side.md
[Cubux.SelfAccount]: ./account.md
