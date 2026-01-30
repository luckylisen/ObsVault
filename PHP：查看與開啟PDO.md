https://pjchender.blogspot.com/2015/08/php-data-objects-pdo.html
https://pjchender.blogspot.com/2015/08/php-data-objects-pdo-2-preparedsql.html

PDO的啟用

檢驗PDO是否啟用

首先，如果你使用的是PHP5.5以上的版本，你很有可能已經有內建PDO，但是你沒使用過，或者還沒啟用而已。

要檢驗PDO是否啟用，請建立一份php文件，輸入

<?
phpinfo();
?>
應該會看到一系列和php有關的資訊，這裡你也可以順便檢視php的版本。



接著搜尋PDO，如果你有找到相對應的欄位和資料庫，表示你的PDO已經啟用了，可以直接進到操作的部分。



如果找不到PDO相關的資料，或者是找到了PDO相關的資料，但是沒有找到你所使用到的資料庫，那麼必須進一步啟用PDO。

開啟PDO

首先透過windows搜尋php.ini，並且打開該文件。



搜尋extension_dir，這裡你可以看到你的擴充功能是放在那個資料夾中。



像我的路徑是c:/appserv/php6/ext

我們就到這個資料夾裡面看一下，看看是不是已經有PDO相關的擴充元件了。這裡我可以看到，我的PHP裡面已經有PDO相關的元件了，代表只是未啟用而已。




啟用PDO的方式很簡單，首先一樣回到php.ini這個文件，接著在剛剛找到的extension_dir下方，可以看到許多的extension相關的元件。

只要把和pdo相關字串，最前面的分號（;）拿掉就可以了，如果你找不到和pdo相關的字串，就請自己加上去，讓它長得向這樣（這裡因為我只用到mysql資料庫，所以我只啟用mysql的pdo，若使用的是不同的資料庫，則根據.dll檔的檔名，套用相關的extension就可以了。



最後重起你的伺服器，再重新去開phpinfo()的頁面，應該就可以看到PDO已經被開啟了。

我這裡使用的apache，所以就直接重新啟動apache伺服器。



沒有PDO套件

如果你們沒有PDO相關的套件的話，除了透過升級PHP來取得之外，可能要自己上網搜尋安裝的方式，這部分就不是這篇文章著墨的地方。

PDO簡易操作

連結資料庫

PDO連結資料庫的方式很簡單，只需要輸入

#連結資料庫
$connection = new PDO('mysql:host=localhost;dbname=pdo_example;charset=utf8', 'root', '12345678');
其中開頭的地方可以選擇資料庫的類型，後面則是資料庫的名稱(dbname)，最後則是資料庫的帳號和密碼。

執行Query

首先，我們可以執行插入資料(Insert Into)的指令，我的資料表包含三個欄位，分別是sn, user和pwd，輸入以下指令，我就可以把資料寫進資料庫中：

#執行Query
$connection->exec('INSERT INTO pdo VALUES ("","PJCHENder", 12345678)');
透過資料的鍵入，我們最後資料表中包含以下資料：




取得Query的結果

最基本的寫法，我們可以直接透過foreach來獲取資料：

#查詢Query的結果
$statement = $connection->query('select * from pdo');

foreach($statement as $row){
    echo $row['user']." ".$row['pwd']."<br>";
}

我們就可以獲得如下的結果：



我們也可以進一步使用while的方式來取的所有的資料：

while($row = $statement->fetch(PDO::FETCH_ASSOC)) {
    echo $row['user'] . ' ' . $row['pwd']."<br>";
}
這裡可以看到我用了一個函式是PDO::FETCH_ASSOC，這裡和過去相似，我們可以把資料以和資料欄位相關的方式叫出資料：



也可以使用PDO::FETCH_NUM來叫出資料：




或者是前面文章提過的，回傳成一個物件，使用PDO::FETCH_OBJ，也可以套用在類別中PDO::FETCH_CLASS，套用在CLASS中的方法可參考(Re-introducing PDO – the Right Way to Access Databases in PHP)，其他的fetch方式，則可參考：PHP PDOStatement:fetch。