
[範例1]
```
<?php
$fruit = "banana";
switch ($fruit) {
    case "banana": 
	    echo "這是一根香蕉";
        break;
    case "apple":
        echo "這是一個蘋果";
        break;
    default:
        echo "未知的水果";
}
?>
```

[範例2]
```
<?php
$level="A";
switch($level){
    case "A":
        echo "表現優良，請繼續保持";
	    break;
    case "B":
        echo "值得肯定，還有進步空間";
	    break;
    case "C":
        echo "需要更多的練習";
	    break;
    case "D":
        echo "需要加強基本功";
	    break;
    default:
        echo "是否無心學業?";
}
?>
```

