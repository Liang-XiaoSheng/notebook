# SQL 快速参考

| **语句**                                                    | **语法**                                                     |
| :---------------------------------------------------------- | :----------------------------------------------------------- |
| AND / OR                                                    | SELECT column_name(s)<br/>FROM table_name<br/>WHERE condition<br/>AND\|OR condition |
| ALTER TABLE (add column)                                    | ALTER TABLE table_name<br/>ADD column_name datatype          |
| ALTER TABLE (drop column)                                   | ALTER TABLE table_name<br/>DROP COLUMN column_name           |
| AS (alias for column)                                       | SELECT column_name AS column_alias<br/>FROM table_name       |
| AS (alias for table)                                        | SELECT column_name<br/>FROM table_name AS table_alias        |
| BETWEEN                                                     | SELECT column_name(s)<br/>FROM table_name<br/>WHERE column_name<br/>BETWEEN value1 AND value2 |
| CREATE DATABASE                                             | CREATE DATABASE database_name                                |
| CREATE TABLE                                                | CREATE TABLE table_name<br/>(<br/>column_name1 data_type,<br/>column_name2 data_type,<br/>.......<br/>) |
| CREATE INDEX                                                | CREATE INDEX index_name<br/>ON table_name (column_name)      |
| CREATE UNIQUE INDEX                                         | CREATE UNIQUE INDEX index_name<br/>ON table_name (column_name) |
| CREATE VIEW                                                 | CREATE VIEW view_name AS<br/>SELECT column_name(s)<br/>FROM table_name<br/>WHERE condition |
| DELETE FROM                                                 | DELETE FROM table_name<br/>WHERE condition<br/>or<br/>DELETE FROM table_name <br/>(**Note:** Deletes the entire table!!)<br/>DELETE * FROM table_name <br/>(**Note:** Deletes the entire table!!) |
| DROP DATABASE                                               | DROP DATABASE database_name                                  |
| DROP INDEX                                                  | DROP INDEX table_name.index_name (SQL Server)<br/>DROP INDEX index_name ON table_name (MS Access)<br/>DROP INDEX index_name (DB2/Oracle)<br/>ALTER TABLE table_name<br/>DROP INDEX index_name (MySQL) |
| DROP TABLE                                                  | DROP TABLE table_name                                        |
| GROUP BY                                                    | SELECT column_name, aggregate_function(column_name)<br/>FROM table_name<br/>WHERE column_name operator value<br/>GROUP BY column_name |
| HAVING                                                      | SELECT column_name, aggregate_function(column_name)<br/>FROM table_name<br/>WHERE column_name operator value<br/>GROUP BY column_name<br/>HAVING aggregate_function(column_name) operator value |
| IN                                                          | SELECT column_name(s)<br/>FROM table_name<br/>WHERE column_name<br/>IN (value1,value2,..) |
| INSERT INTO                                                 | INSERT INTO table_name<br/>VALUES (value1, value2,....)<br/>*or*<br/>INSERT INTO table_name<br/>(column_name1, column_name2,...)<br/>VALUES (value1, value2,....) |
| INNER JOIN                                                  | SELECT column_name(s)<br/>FROM table_name1<br/>INNER JOIN table_name2<br/>ON table_name1.column_name=table_name2.column_name |
| LEFT JOIN                                                   | SELECT column_name(s)<br/>FROM table_name1<br/>LEFT JOIN table_name2<br/>ON table_name1.column_name=table_name2.column_name |
| RIGHT JOIN                                                  | SELECT column_name(s)<br/>FROM table_name1<br/>RIGHT JOIN table_name2<br/>ON table_name1.column_name=table_name2.column_name |
| FULL JOIN                                                   | SELECT column_name(s)<br/>FROM table_name1<br/>FULL JOIN table_name2<br/>ON table_name1.column_name=table_name2.column_name |
| LIKE                                                        | SELECT column_name(s)<br/>FROM table_name<br/>WHERE column_name<br/>LIKE pattern |
| ORDER BY                                                    | SELECT column_name(s)<br/>FROM table_name<br/>ORDER BY column_name [ASC\|DESC] |
| SELECT                                                      | SELECT column_name(s)<br/>FROM table_name                    |
| SELECT *                                                    | SELECT *<br/>FROM table_name                                 |
| SELECT DISTINCT                                             | SELECT DISTINCT column_name(s)<br/>FROM table_name           |
| SELECT INTO<br/>(used to create backup copies of tables)    | SELECT \*<br/>INTO new_table_name [IN external database]<br/>FROM original_table_name<br/>*or*<br/>SELECT column_name(s)<br/>INTO new_table_name [IN external database]<br/>FROM original_table_name |
| SELECT TOP                                                  | SELECT TOP number\|percent column_name(s)<br/>FROM table_name |
| TRUNCATE TABLE<br/>(deletes only the data inside the table) | TRUNCATE TABLE table_name                                    |
| UNION                                                       | SELECT column_name(s) FROM table_name1<br/>UNION<br/>SELECT column_name(s) FROM table_name2 |
| UNION ALL                                                   | SELECT column_name(s) FROM table_name1<br/>UNION ALL<br/>SELECT column_name(s) FROM table_name2 |
| UPDATE                                                      | UPDATE table_name<br/>SET column_name=new_value<br/>[, column_name=new_value,....]<br/>WHERE column_name=some_value |
| WHERE                                                       | SELECT column_name(s)<br/>FROM table_name<br/>WHERE condition |