```
catch (PDOException $e) { 
	// $e 本身就知道自己發生了什麼事
	die($e->getMessage()); }
```
