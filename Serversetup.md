---------------------------------------------------------
---------------------------------------------------------


kill -9 <processID>

nohup java -jar -Xmx256m &

nohup java -jar -Xmx256m  abc.jar &\

nohup java -jar app.jar &

curl -v url
  
npm install --legacy-peer-deps

process id-- 2401

inbound rules--  instance -- 

https://dba.stackexchange.com/questions/271981/access-denied-you-need-at-least-one-of-the-process-privileges-for-this-ope#

------------------------------------------- sql ------------------------------------------------
'Access denied; you need (at least one of) the PROCESS privilege(s) for this operation' when trying to dump tablespaces
------------------------------------------------------------------------------------------------

--solution not working ----
GRANT PROCESS ON db.* TO user@localhost;

For priliages--
GRANT ALL PRIVILEGES ON db.* TO 'user'@'localhost' WITH GRANT OPTION

FLUSH PRIVILEGES;

mysql--
https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04

export dump--f
mysqldump --no-tablespaces -u user_name -p db_Name > backup_file.sql

import dump--
mysqldump --no-tablespaces -u user -p password < tabledump.sql


-Xmx256m

ps aux | grep -i firefox

npm run-script build
--------------------

kill -3 pid --> for stack trace
jcmd <PID> Thread.print
jstack **8536** > threadDump.log

-----------------------
sql ---
show status where `variable_name` = 'Threads_connected';
show processlist;
SHOW STATUS WHERE `variable_name` = 'Max_used_connections';
