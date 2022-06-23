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

sudo rm /var/lib/docker/overlay2/* -r

sudo systemctl start docker.socket
sudo systemctl start docker
```



