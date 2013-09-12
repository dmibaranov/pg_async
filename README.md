Overview
========

This a simple application with two gevent loops
* loop_log - print a current datestamp every second
* loop_database - execute `select pg_sleep(5);` query every second


Usage
=====

	python -m pg_async.test -h
	usage: test.py [-h] [--enable-psycogreen] connection_string
    
	Simple psycogreen sample app
    
	positional arguments:
	  connection_string    Database connection string, eg:
	                       user:password@127.0.0.1:5432/database

	optional arguments:
	  -h, --help           show this help message and exit
	  --enable-psycogreen  Enable psycogreen


Results
=======

	$ python -m pg_async.test gigs:123@127.0.0.1:5432/gigs                    
	Log: 2013-09-12 23:40:55.309311
	Database: OK
	Log: 2013-09-12 23:41:00.334055
	Database: OK
	Log: 2013-09-12 23:41:06.340996
	Database: OK
	Log: 2013-09-12 23:41:12.353856
	^C

	$ python -m pg_async.test gigs:123@127.0.0.1:5432/gigs --enable-psycogreen
	Log: 2013-09-12 23:41:47.521231
	Log: 2013-09-12 23:41:48.526269
	Log: 2013-09-12 23:41:49.531905
	Log: 2013-09-12 23:41:50.537845
	Log: 2013-09-12 23:41:51.546597
	Database: OK
	Log: 2013-09-12 23:41:52.550962
	Log: 2013-09-12 23:41:53.558002
	Log: 2013-09-12 23:41:54.558698
	Log: 2013-09-12 23:41:55.565481
	Log: 2013-09-12 23:41:56.567456
	Log: 2013-09-12 23:41:57.574333
	Database: OK
	Log: 2013-09-12 23:41:58.580712
	Log: 2013-09-12 23:41:59.583251
	Log: 2013-09-12 23:42:00.590544
	^C

