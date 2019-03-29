# Feed-The-Beast Interactions (Modded Minecraft 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_ultimate_reloaded:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_ultimate_reloaded_data
docker volume create minecraft_ftb_ultimate_reloaded_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_ultimate_reloaded \
    --volume minecraft_ftb_ultimate_reloaded_data:/minecraft/world \
    --volume minecraft_ftb_ultimate_reloaded_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_ultimate_reloaded:stable
```
ultimate_reloaded