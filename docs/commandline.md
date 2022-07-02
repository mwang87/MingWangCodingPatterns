## Determine life of SSD

```
sudo smartctl -t short -a /dev/sda
```

## Setup new SSD on workstation

Check the device name

```
lsblk
```

Use gparted in UI

## Docker Cleanup

If docker is being annoying and creating a ton of stuff in the overlay2 folder even though docker system df is clear. To fully clear Docker do the following


Clear the official documents

```
docker system clean -af
```

Clear overlay2 which is major surgery on docker

```
sudo systemctl stop docker.socket
sudo systemctl stop docker

sudo rm /var/lib/docker -r

sudo systemctl start docker.socket
sudo systemctl start docker
```

## SQLITE3 Dump Resoration

If you have a database corruption and need to recreate a Sqlite3 Database, you can use the following commands:

```
cat db.schema | sqlite3 database.db
cat db.dump | | sqlite3 database.db
```

NOTE: Its important to use the schema because the ordering of the columns might not actually be correct on the original database and you'll get scrambled columns if you don't do this. 

## SSH Security

How to disable password SSH - [link](https://www.cyberciti.biz/faq/how-to-disable-ssh-password-login-on-linux/)
