CP-BackupTool
=============

backup and restore tool for CouchPotato's wanted list.

After cloning this repo you need to edit the couch.cfg to add your correct host, path and apikey (from CouchPotato, settings, general)
You can also specify the path to a CFG file:
```
./wanted.py --type backup --cfg /your/path/cfg /volume1/Public/backup.txt
```

###### Backup
To create a backup of your wanted movies, run the script passing in the options "backup" and the full path/name of the backup file you want to create
```
./wanted.py --type backup /volume1/Public/backup.txt
```

###### Restore
Now, should your database need to be deleted, or is otherwise lost, set up the quality profiles, do a full manage scan (to make sure we don't add and snatch movies that were already downloaded since your last backup) and then run this script with the option "restore" followed by the path to the backup file.
(NOTE: If you did a complete re-install, you will need to enter the NEW api key in the couch.cfg)
```
./wanted.py --type restore /volume1/Public/backup.txt
```

This doesn't assign a specific quality or category... you will need to manually edit these in the wanted list.
In case you are worries about auto-snatch with the wrong quality etc (not default) I suggest setting your downloader to "manual" to prevent auto-snatching, before running the restore. Take the downloader out of "manual" mode once you are comfortable all has been restored correctly.

###### More options
To see all options for wanted.py:
```
./wanted.py -h
```
