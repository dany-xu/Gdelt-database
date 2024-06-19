# Gdelt-database

This is the README file for gdelt Postgres database. Data range from 2015/02/17 23:00:00 till now.

## task

* download zip from [Master CSV Data File List -English](http://data.gdeltproject.org/gdeltv2/masterfilelist.txt):  

  https://blog.gdeltproject.org/gdelt-2-0-our-global-world-in-realtime/

* clean the data 

* insert into Postgres database

* update database every 15 minutes from [Last 15 Minutes CSV Data File List -English](http://data.gdeltproject.org/gdeltv2/lastupdate.txt)

## file storing instruction

* The codes and logging files are stored in file "gdelt database" at Desktop.

* The csv data is stored in hard drive "/T5EVO/postgres_data" where missing time name are stored as null file is in the same file as well.
* The database data is stored in hard drive "/T5EVO/postgres/base" which is moved from default postgresql data path. 

## log txt instruction

2015 - 2017

* The error messages, downloading time, inserting time are stored in "insertion_log_{year}.txt"
* The missing time file names are stored in "error_url_{year}.txt"

2018 - 2024

* The error messages and downloading time are stored in "downloading_log_{year}.txt"
* 

## gdelt_sql_insert.ipynb:

This is the codes for the data cleaning and "Master CSV Data File List -English" inserting. 

There are mainly two methods used to insert. 

1. After downloading zip, do the insertion immediately by using  `insert_into_database(final_all, database_url, names[0])`. The logic is to write into the database row by row, which led to huge data insertion time from 2017/02. 
2. After downloading the zip for a whole year, use the stored csv to insert by using copy method. 

There are also other parts of code for small functions used such as checking the missing csv that is downloaded but not inserted, and align the table names in the same format etc.

## auto15_gdelt.py:

This is the code file for automatically database update.

To run it use terminal:

1.  `chmod +x /Users/macglobalai/Desktop/Gdelt\ Database/auto15_gdelt.py`

2.  open backstage running: `crontab -e`

3.  add to schedule: `*/15 * * * * /anaconda3/bin/python3.7 /Users/macglobalai/Desktop/Gdelt\ Database/auto15_gdelt.py`

4.  save and exit

To terminate: 

`pkill -f auto15_gdelt.py`This is the README file for gdelt Postgres database. Data range from 2015/02/17 23:00:00 till now.

## task

* download zip from [Master CSV Data File List -English](http://data.gdeltproject.org/gdeltv2/masterfilelist.txt):  

  https://blog.gdeltproject.org/gdelt-2-0-our-global-world-in-realtime/

* clean the data 

* insert into Postgres database

* update database every 15 minutes from [Last 15 Minutes CSV Data File List -English](http://data.gdeltproject.org/gdeltv2/lastupdate.txt)

## file storing instruction

* The codes and logging files are stored in file "gdelt database" at Desktop.

* The csv data is stored in hard drive "/T5EVO/postgres_data" where missing time name are stored as null file is in the same file as well.
* The database data is stored in hard drive "/T5EVO/postgres/base" which is moved from default postgresql data path. 

## log txt instruction

2015 - 2017

* The error messages, downloading time, inserting time are stored in "insertion_log_{year}.txt"
* The missing time file names are stored in "error_url_{year}.txt"

2018 - 2024

* The error messages and downloading time are stored in "downloading_log_{year}.txt"
* 

## gdelt_sql_insert.ipynb:

This is the codes for the data cleaning and "Master CSV Data File List -English" inserting. 

There are mainly two methods used to insert. 

1. After downloading zip, do the insertion immediately by using  `insert_into_database(final_all, database_url, names[0])`. The logic is to write into the database row by row, which led to huge data insertion time from 2017/02. 
2. After downloading the zip for a whole year, use the stored csv to insert by using copy method. 

There are also other parts of code for small functions used such as checking the missing csv that is downloaded but not inserted, and align the table names in the same format etc.

## auto15_gdelt.py:

This is the code file for automatically database update.

To run it use terminal:

1.  `chmod +x /Users/macglobalai/Desktop/Gdelt\ Database/auto15_gdelt.py`

2.  open backstage running: `crontab -e`

3.  add to schedule: `*/15 * * * * /anaconda3/bin/python3.7 /Users/macglobalai/Desktop/Gdelt\ Database/auto15_gdelt.py`

4.  save and exit

To terminate: 

`pkill -f auto15_gdelt.py`
