# rmandeploy
rman deploy script
Since we do not have a reliable location to store our script I am using this to store my script.
To run this script, just download it then run like this:
sh ./rmandeploy.sh
10/17/2017 
Right now the this script is a stand alone script that will deploy rman backup script to the server. The script would go like this. 
1. Check zfs is mounted. Script will execute if not mounted. 
2. Check if database exist in the server, script will execute if no database. 
3. It will run through the databases in oratab(will have to modify this so it will run only once.)
  3.1 While running through the databases, it check for 
    3.1.1 DB Version
    3.1.2 Encryption status
    3.1.3 Existince of Bigfile
4. Download the needed scripts from depot. 
5. Decide which template to use.(based on step 3.)
6. Set the crontab.
7. Run first full backup(Still inprogress).

TODO:
1. Version detection: Since some sql does not work on some version esp 10Gr1 versions.
2. Multi-tenant and single tenant detection: Current sql does not work on single and multi tenant
3. Incorporate Level 1 backup piece validation.
