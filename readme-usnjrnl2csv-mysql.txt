As of version 1.0.0.7, the output csv of usnjrnl2csv supports import into MySql database. Attached is the database schema, usnjrnl2csv.sql, which should be used to create the database on MySql 5.6.4 or higher. That version is when precision in the timestamp was added. Earlier versions can be used, but then all DATETIME(6) occurrences in usnjrnl2csv.sql must be replaced with VARCHAR(28). It is important to use timestamp format 6. Precision of MilliSec or NanoSec is optional, but recommended. If NanoSec precision is used, then precision separator 2 must be empty (default value). It is also important to keep the timestamp error value to something valid for MySql, which the default value is. A nice sql client to use is HeidiSql. To import the csv into the database, use the import-csv-usnjrnl.sql. Remember to change the path to csv at the top of file, and also the separator if the default was changed. Alternatively just use the autogenerated sql that will have correct settings anyway.

For manual database creation use following statement:

CREATE DATABASE IF NOT EXISTS Ntfs
	CHARACTER SET 'utf8'
	COLLATE 'utf8_general_ci';

