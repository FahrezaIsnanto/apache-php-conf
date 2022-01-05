# How to Setup PHP 7.2, Apache and MySQL in Windows 10

1. First is to download php 7 to this website https://windows.php.net/download/
    - download VC15 x86 or x64 Thread Safe
    - download x86 for 32bit and x64 for 64bit system

2. Make a directory and save it to this path C:/php 

3. Go to https://www.apachelounge.com/download/ to download the Apache server
    - Download Apache 2.4.39 Win64 or Apache 2.4.39 Win32
    - Extract the zip file to C:/Apache 24
    - next is to open your cmd cd to bin directory
    - type: httpd.exe  // to start apache server
    - go to "conf/httpd.conf" open it on texteditor, paste this code at the top

			LoadModule php7_module "c:/php/php7apache2_4.dll"
			AddHandler application/x-httpd-php .php
			# configure the path to php.ini
			PHPIniDir "c:/php"
				
    - search for ServerName uncomment change "www.example.com:80" to "localhost" or "127.0.0.1:80"

    - go to Apache24/htdocs/ change index.html to index.php    	
    - Run the server c:\Apache24\bin\httpd -k install (required visual c++ 2015 to up)
    - To see the settings c:\Apache24\bin\httpd -k install

4. Next is to search for "Edit the system environment variables"
    - click Environment Variables > System variables 
    - find 'Path' on the list double click it and add these ff.
        
			C:\php
			C:\Apache24
			C:\Apache24\bin    
    
     - then click ok to save
     - note: this allows you to run php scripts standalone.

5. Next go to php directory change the file "php.ini-development" into "php.ini"

6. open the php.ini uncomment some codes @ line 885

			extension=gd2
			extension=mysqli
			extension=pdo_mysql
			extension=pdo_pgsql
			extension=pdo_sqlite
			extension=pgsql
			extension_dir = "ext"
			mbstring
			extension=fileinfo


## How to Add MySQL to your path

<p>Locate your msyql.exe</p>

    C:\Program Files\MySQL\MySQL Server 5.7\bin

- Right click "My Computer"
- Select "Advanced"
- Click "Environment Variables"
- Locate "System variables"
- Select the "path" variable
- Click "Add" 
- Paste the mysql path
