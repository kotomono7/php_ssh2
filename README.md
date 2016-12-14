# PHP SSH2

## About
This is a simple function to connect with sftp server using php and ssh2 lib

## Requirements
PHP >= 5, libssh2-1, libssh2-1-dev, libssh2-php, pecl ssh2 (https://pecl.php.net/package/ssh2)

## How To
```php
<?php

include("ftp_class.php");

try {
      // connect and login to sftp server
      $sftp = new SFTPConnection("ip_address_or_domain_name", port);
      $sftp->login("username", "password");
      echo "Connected to sftp server.";  
      
      // read file on sftp server
      $data = $sftp->readFile("/home/username/file.txt");
      echo '<pre>';
      print_r($data);
      echo '</pre>';
      
      // read .csv file on sftp server and convert it to arrays
      $csv = $sftp->readCSV("/home/username/data.csv");
      echo '<pre>';
      print_r($csv);
      echo '</pre>';
      
      // scan folder on sftp server
      $scan = $sftp->scanFilesystem("/folder_name");
      echo '<pre>';
      print_r($scan);
      echo '</pre>';
} catch (Exception $e) {
      echo $e->getMessage()."\n";
}
  
?>
```

Voila!!!
