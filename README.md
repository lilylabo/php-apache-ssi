Containerize This: PHP/Apache/MySQL
===================================

## Files
```
/php-apache-mysql/
├── apache
│   ├── Dockerfile
│   └── demo.apache.conf
├── docker-compose.yml
├── php
│   └── Dockerfile
└── public_html
    └── index.php
```

URL: http://localhost:80 

to see the demo. 

#### index.php
```
<h1>Hello Demo!</h1>
<h4>Attempting MySQL connection from php...</h4>
<?php
$host = 'mysql';
$user = 'root';
$pass = 'pass';
$conn = new mysqli($host, $user, $pass);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
} else {
  echo "Connected to MySQL successfully!";
}
?>
```
Test connect to a MySQL database using the mysqli interface from PHP. Display successful or failed message. 

### .env
```
PHP_VERSION=8.0
MYSQL_VERSION=8.0
APACHE_VERSION=2.4.61

DB_ROOT_PASSWORD=pass
DB_NAME=database
DB_USERNAME=user
DB_PASSWORD=password

PROJECT_ROOT=./public_html
```