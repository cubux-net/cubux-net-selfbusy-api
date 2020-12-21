Тип `Cubux.SelfCategoryOperationLink`
============================

Связь между операциями расхода по категориям
[`Cubux.SelfCategoryOperation`][Cubux.SelfCategoryOperation] и доходными
категориями
[`Cubux.SelfCategory`][Cubux.SelfCategory].

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`income_uuid`** PK  | `uuid` | UUID операции доходов
**`expense_uuid`** PK | `uuid` | UUID операции расходов


[Cubux.SelfCategoryOperation]: ./category.md
[Cubux.SelfCategoryOperation]: ./category-operation.md
