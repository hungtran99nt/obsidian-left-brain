| Implicit Cursor                                       | Explicit cursor                                              |
| ----------------------------------------------------- | ------------------------------------------------------------ |
| Trả về 1 single row value                             | Trả về returns của 1 subquery, các row này là **ACTIVE SET** |
| Dùng cho DML operations (DECLARE, OPEN, FETCH, CLOSE) | Dùng cho Multirow SELECT Statements                          |
| Có thể handle NO_DATA_FOUND exception                 | Không handle được NO_DATA_FOUND exception                                                             |
