EP1 ออกแบบหน้าเว็บไซต์ด้วย Bootstrap
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


# EP3 แสดงข้อมูลบนหน้าเว็บไซต์และ ทำระบบหมวดหมู่
```php 

```
