# Hacks-Life-
This repo is devoted to some amazing tips and tricks for solving some challenging situations in tech where we stuck. Explore this repo . It is open to the collaboration and is under ongoing development

### Export VERY LARGE FILE(>2GB) from mysql :
<br /> Follow the below instructions :
<br /> Got to your mysql console : `mysql -u username_mysql -p` . Then press `enter` and  it will ask for password . Enter the password.
<br /> Now in console .Go to db in which the table is located : `use database_name ;` . 
<br /> Now Enter the command to import table (VERY LARGE) .
```
SELECT column1 , column , column3.....
FROM table_name
WHERE enter_condition,if
INTO OUTFILE '/var/lib/mysql-files/file_name.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n';
```
<br />If it will give `file-priv` error . Then type : `SHOW VARIABLES LIKE "secure_file_priv";`
<br /> It will give u a directory where u can save that file . Just replace that directory in above code in `OUTFILE` line
<br /> And it will export the `VERY LARGE file` in just some couple of minutes . A super fast method to do !!! 

### IMPORT VERY LARGE  `CSV `FILE(>2GB) into mysql :
<br /> Follow the below instructions :
<br /> Got to your mysql console : `mysql -u username_mysql -p` . Then press `enter` and  it will ask for password . Enter the password.
<br /> Now in console .Go to db in which the table is located : `use database_name ;` . 
<br /> Now Enter the command to import table (VERY LARGE) .
```
LOAD DATA INFILE "/var/lib/mysql-files/data.csv"
INTO TABLE CSVImport
COLUMNS TERMINATED BY ','
OPTIONALLY ENCLOSED BY '"'
ESCAPED BY '"'
LINES TERMINATED BY '\n'
```
<br />If it will give `file-priv` error . Then type : `SHOW VARIABLES LIKE "secure_file_priv";`
<br /> It will give u a directory where u can save that file . Just replace that directory in above code in `INFILE` line
<br /> And it will import the `VERY LARGE file` in just some couple of minutes . A super fast method to do !!! 
