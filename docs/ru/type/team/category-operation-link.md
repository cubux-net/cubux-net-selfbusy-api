Тип `Cubux.SelfCategoryOperationLink`
============================

Связь между операциями расхода по категориям
[`Cubux.SelfCategoryOperation`][Cubux.SelfCategoryOperation] и доходными
категориями
[`Cubux.SelfCategory`][Cubux.SelfCategory].

Объект со следующими полями:

Поле | Тип | Описание
---- | --- | --------
**`expense_op_uuid`** PK | `uuid` | UUID операции расхода по категории
**`income_cat_uuid`** PK  | `uuid` | UUID категории доходов


[Cubux.SelfCategoryOperation]: ./category.md
[Cubux.SelfCategoryOperation]: ./category-operation.md
