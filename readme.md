#MYSQL ADVANCED
By Simon
hiennv219.github.io
Skype: nvhien129@hotmail.com

--------------------------------------------------------------
#Control flow functions

(Link: http://dev.mysql.com/doc/refman/5.7/en/control-flow-functions.html)


##IF

	IF(expr1,expr2,expr3)

	Nếu `expr1` ĐÚNG thì TRẢ VỀ `expr2`, SAI thì TRẢ VỀ `expr3`

Example:

	mysql> SELECT IF(1>2,2,3);
        -> 3

##IFNULL

	IFNULL(expr1,expr2)

	Nếu `expr1` NOTNULL thì trả về `expr1`, Không trả về `expr2` ( Tức là `expr1` NULL)

Example:

	mysql> SELECT IFNULL(1,0);
        -> 1

##NULLIF
	
	NULLIF(expr1, expr2)

	Nếu `expr1` = `expr2` Thì trả về NULL, Không thì trả về giá trị của `expr1`

Example:

	mysql> SELECT NULLIF(1,1);
        -> NULL

##CASE

####`CASE` có 2 dạng: `CASE` có VALUE và `CASE` Không có VALUE

######CASE 1: Có `value`

	CASE value WHEN [compare_value] THEN result [WHEN [compare_value] THEN result ...] [ELSE result] END

	Nếu value = compare_value Thì trả về kết quả ở trường hợp đó, Không thì trả về ELSE.

Example:

	mysql> SELECT CASE 1 WHEN 1 THEN 'one'
				    ->   WHEN 2 THEN 'two'
				    ->	 ELSE 'more' END;

        -> Kết quả: 'one'


######CASE 2: Không `value`

	CASE WHEN [condition] THEN result [WHEN [condition] THEN result ...] [ELSE result] END

	Nếu condition Đúng thì trả về kết quả. Không thì trả về ELSE.

Example:

	mysql> SELECT CASE WHEN 1>0 THEN 'true' ELSE 'false' END;
        -> 'true'


Note: Ở 2 trường hợp nếu không có ELSE thì giá trị trả về mặc định là NULL



