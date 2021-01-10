# EP1 ออกแบบหน้าเว็บไซต์ด้วย Bootstrap
```css
.card {
        font-weight: 400;
        border: 0;
        border-radius: 25px;
        box-shadow: 0 2px 5px 0 rgba(0, 0, 0, 0.16), 0 2px 10px 0 rgba(0, 0, 0, 0.12);
    }
```


# EP2 เชื่อมต่อฐานข้อมูลและสร้างตารางและ Insert ข้อมูล
```php 
<?php
  // การเชื่อมต่อฐานข้อมูล
 define('DB_SERVER','localhost');
 define('DB_USER','root');
 define('DB_PASS','');
 define('DB_NAME','Thanadon');

try {
  $pdo = new PDO("mysql:host=".DB_SERVER.";dbname=".DB_NAME, DB_USER, DB_PASS);
  // เช็คการเชื่อมต่อฐานข้อมูล
  $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
  echo "การเชื่อมต่อฐานข้อมูลสำเร็จ" ;
} catch(PDOException $e) {
  echo "การเชื่อมต่อฐานข้อมูลผิดพลาด กรุณาลองใหม่อีกครั้ง: " . $e->getMessage();
}

?>

//สร้างฐานข้อมูล
ID
ID_group
image
title
desc
date
```


# EP3 จัดระเบียบโค้ดให้เรียบร้อยด้วยภาษา PHP
```php 

    <?php

        if ($_GET['page'] == "home") {
            include('page/home.php');
        } else if ($_GET['page'] == "register") {
            include('page/register.php');
        } else if ($_GET['page'] == "login") {
            include('page/login.php');
        } else if ($_GET['page'] == "detail") {
            include('page/detail.php');
        } else {
            include('page/home.php');
        }
    ?>
    
    
```

# EP4 แสดงข้อมูลบนหน้าเว็บไซต์และ ทำระบบหมวดหมู่ 

```php 
        $sql = $pdo->prepare("SELECT * FROM news");
        $sql->execute();
        $result = $sql->fetchAll();
        foreach ($result as $res){}
    
```


# EP5 ออกแบบและ ทำระบบ Details เพื่อแสดงรายละเอียด

```php 

if (isset($_GET['id'])) {
    $id = $_GET['id'];
}

$result = $pdo->query("SELECT * FROM news WHERE id = $id");
while ($data = $result->fetch(PDO::FETCH_ASSOC)) {
        print_r($data);
    }
    
```
