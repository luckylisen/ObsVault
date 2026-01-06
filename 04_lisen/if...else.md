[從上而下，依序判斷，執行完就跳出]
```
if($score<=59){
    echo  "E";
    exit();
}

if($score<=69){
    echo  "D";
    exit();
}

if($score<=79){
    echo  "C";
    exit();
}

if($score<=89){
    echo  "B";
    exit();
}

if($score<=100){
    echo  "A";
    exit();
}
```

[範例2]
```
if($score>=0 && $score<=59){
    $level="E";
}else if($score<=69){
    $level="D";
}else if($score<=79){
    $level="C";
}else if($score<=89){
    $level="B";
}else if($score<=100){
    $level="A";
}else{
    $level="分數錯誤";
}
echo $level;
```

[三元判斷式]
```
$score=99;
if($score>=60){
    echo "及格";  //true
}else{
    echo "重考";  //false
}

$score=99;
$result=($score>=60)?'及格':'重考';
```

[潤年判斷]
```
<h2>判斷是否為閏年</h2>
<ul>
    <li>地球公轉一年大約是365天5小時48分46秒，所以每4年設1閏年來消除這多出來的1天</li>
    <li>不可整除4：平年。</li>
    <li>可以整除4，但不可整除100：閏年。</li>
    <li>可以整除100，但不可整除400：平年。</li>
</ul>

<?php
$this_year=3000;
echo $this_year."是";
if ($this_year % 4 != 0){
    echo "平年";
}else{
    if($this_year % 100 != 0){
        echo "潤年";
    }else{
        if($this_year % 400 != 0){
            echo "平年";
        }else{
            echo "潤年";
        }
    }
}
?>
```