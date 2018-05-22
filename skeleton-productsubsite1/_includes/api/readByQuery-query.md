SQL-like query based on fields on the `object`. Illegal XML characters must be properly encoded. The following SQL operators are supported: `<`, `>`, `>=`, `<=`, `=`, `like`, `not like`, `in`, `not in`. When doing NULL comparisons: `IS NOT NULL`, `IS NULL`. Multiple fields may be matched using the `AND` and `OR` operators. Joins are not supported. Single quotes in any operands must be escaped with a backslash - For example, the value `Erik's Deli` would become `'Erik\'s Deli'`.