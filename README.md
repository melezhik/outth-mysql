# SYNOPSIS

outthentic tests for mysql server

# Usage

    sparrow index update
    sparrow plg install outth-mysql
    sparrow project create mysql
    sparrow check add mysql outth-test
    sparrow check set mysql outth-test outth-mysql 127.0.0.1
    sparrow check ini mysql outth-test outth-mysql

        [mysql]
        user     = root
        password = 123
        port     = 3306

    sparrow check run mysql outth-test
     
# Check list

* verifies that select User,Host from mysql.user return valid data

* verifies that simple CRUD operations work 

    * create,delete database 
    * create table
    * insert into table
    * select from table

# Sample Output

    ok 1 - stdout is already set
    ok 2 - stdout saved to /tmp/.outthentic/10889/n9EnaOJQaQ
    ok 3 - [b] output match 'SELECT Host,User FROM user WHE'
    ok 4 - [b] output match 'Host : 127.0.0.1 User: root'
    ok 5 - [b] output match 'SELECT Host,User FROM user WHE'
    ok 6 - [b] output match 'Host : localhost User: root'
    1..6
    ok
    /tmp/.outthentic/10889/home/vagrant/my/outth-mysql/simple-crud/story.t ........
    ok 1 - stdout is already set
    ok 2 - stdout saved to /tmp/.outthentic/10889/NncaId4Zfv
    ok 3 - [b] output match 'create database foo'
    ok 4 - [b] output match 'Affected row: 1'
    ok 5 - [b] output match 'create table foo.bar (name tex'
    ok 6 - [b] output match 'Affected row: 0'
    ok 7 - [b] output match 'insert into foo.bar (name) val'
    ok 8 - [b] output match 'Affected row: 1'
    ok 9 - [b] output match 'SELECT name from foo.bar'
    ok 10 - [b] output match 'Name : alexey'
    1..10
    ok
    All tests successful.
    Files=2, Tests=16,  0 wallclock secs ( 0.03 usr  0.00 sys +  0.11 cusr  0.01 csys =  0.15 CPU)
    Result: PASS
    
# Author

Alexey Melezhik
    
