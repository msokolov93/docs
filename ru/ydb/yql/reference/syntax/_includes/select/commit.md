---
sourcePath: ru/ydb/ydb-docs-core/ru/core/yql/reference/yql-core/syntax/_includes/select/commit.md
sourcePath: ru/ydb/yql/reference/yql-core/syntax/_includes/select/commit.md
---
## COMMIT {#commit}

По умолчанию весь YQL запрос выполняется в рамках одной транзакции и независимые его части внутри выполняются по возможности параллельно.
С помощью ключевого слова `COMMIT;` можно добавить барьер в процесс выполнения, чтобы отложить выполнение идущих следом выражений до тех пор, пока не выполнятся все предшествующие.

Чтобы коммит выполнялся аналогичным образом автоматически после каждого выражения в запросе, можно использовать `PRAGMA autocommit;`.

**Примеры:**

``` yql
INSERT INTO result1 SELECT * FROM my_table;
INSERT INTO result2 SELECT * FROM my_table;
COMMIT;
-- В result2 уже будет содержимое SELECT со второй строки:
INSERT INTO result3 SELECT * FROM result2;
```