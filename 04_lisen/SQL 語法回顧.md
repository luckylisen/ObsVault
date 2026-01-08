[創建]
```
CREATE TABLE students (
	id INT AUTO_INCREMENT PRIMARY KEY,
	name VARCHAR(50),
	mobile VARCHAR(20) 
);
```
==`AUTO_INCREMENT = 自動遞增`==
==`PRIMARY KEY = 主鍵`==

[新增]
```
INSERT INTO
    `students` (`id`, `name`, `mobile`)
VALUES
    (NULL, 'amy', '0911'),
    (NULL, 'bob', '0922'),
    (NULL, 'cat', '0933'),
    (NULL, 'dog', '0944');
```

[修改]
```
UPDATE
    `students`
SET
    `mobile` = '0922-123'
WHERE
    `students`.`id` = 2;
```

[刪除]
```
DELETE FROM
    `students`
WHERE
    `students`.`id` = 3;
```

[查詢]
```
SELECT
    *
FROM
    `students`
WHERE
    `students`.`id` = 4;
```

```
D table C V C
U table Set ?
D from table ?
S * frome table ?
```

[資料庫結構(schema) ]

|        | ==student== |          |
| :----: | :---------: | :------: |
| column |     中文      |   type   |
|   id   |     序號      | int(10)  |
|  name  |     姓名      | char(10) |
| mobile |     電話      | char(10) |
