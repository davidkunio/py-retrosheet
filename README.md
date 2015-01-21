YE REQUIREMENTS
-
Chadwick 0.6.2 http://chadwick.sourceforge.net/
python 2.5+ (don't know about 3.0, sorry)
sqlalchemy: http://www.sqlalchemy.org/
[if using postgres] pyscopg2 python package (dependency for sqlalchemy)

1. create database called <code>retrosheet</code> (or whatever)
2. add schema to the database w/ the included SQL script (the .postgres.sql one works nicely w/ PG, the other w/ MySQL)
3. configure the file <code>db.ini</code> with your appropriate ENGINE, USER, HOST, PASSWORD, DATABASE values - if yer using postgres, you can optionally define SCHEMA and download directory
 * valid values for ENGINE are valid sqlalchemy engines e.g. 'mysql', 'postgresql' or 'sqlite'
 * if you have your server configured to allow passwordless connections, you don't need to define USER and PASSWORD
 * if you are using sqlite3, 'database' in the config should be the path to your database file
 * specify directory for retrosheet files to be downloaded to, needs to exist before script runs
4. run <code>download.py</code> to download the files from retrosheet's servers (optionally use <code>-y XXXX</code> to get only a certain year)
5. run <code>parse.py</code> to parse the files and insert the data into the database. (optionally use <code>-y XXXX</code> to import just one year)

YE GRATITUDE
-
Github user jeffcrow made many fixes and additions and added sqlite support

JUST THE DATA
-
If you're using PostgreSQL (and you should be), you can get a dump of all data up through 2014 (warning: 502MB) [here](https://www.dropbox.com/s/03c3zyk91c2yfuw/retrosheet.sql.gz
)
