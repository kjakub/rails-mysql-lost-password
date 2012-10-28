rails-mysql-lost-password
=========================

If you are rails developer and you have lost password for mysql :

This answer is in connection with Ruby on Rails framework where this behavior occurred
 

 1. have mysql with user root and password 
 2. bootstrap new rails project
    using with mysql "rails new projectname  
        -d mysql" 
 3. do not modify config/database.yml - defaults credentials for server are name: root, password is blank 
 4. rake db:create prompt show up - asking for root password and then when you provide root password

the answer is in GRANT command on line 68 in [here][1]


  [1]: https://github.com/rails/rails/commit/64756e8f718c90a17664f2d35993696d8bf0f81e

basically it executed GRANT command with credentials matches your current database.yml

I have discussed this topic and behavior will improved and it is taken and reported as a bug. 


http://serverfault.com/questions/283549/mysql-loses-its-root-password/443132#443132
http://stackoverflow.com/questions/12085022/yes-another-mysql-error-1045-28000-access-denied-for-user-rootlocalhost/13113667#13113667
http://stackoverflow.com/questions/9297677/mysql-error-1045-after-rake-dbcreate/13113643#13113643