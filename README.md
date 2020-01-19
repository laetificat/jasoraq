# Jasoraq
Jasoraq is a combination of **Ja**ckett **So**narr **Ra**darr **q**Bittorrent.

## Usage
- Make sure you have docker installed.  
- Copy the .env.example to .env with `cp .env.example .env`
- Edit the .env file to change the configuration, only GID and UID is needed
- Run `docker-compose up -d`

Now you should have all the services running, you can check with docker-compose ps to see which ports are used.  
By default the following ports are used:  
```
Jackett: 9117
Sonarr: 8989
Radarr: 7878
qBittorrent: 8888
```

By default everything that is mounted will be in ~/.jasoraq, including all the downloads.  

### Configuring
You still need to configure Jackett, Sonarr, and Radarr.

#### Configuring Jackett
Go to `localhost:9117` and add a new tracker.

#### Configuring Radarr
- Go to `localhost:7878`
- Go to settings
- Click on `Indexers`
- Add a new custom Torznab
- Use the settings from Jackett
- Change the `localhost` part in the url to `jackett`
- Go to `Download Client`
- Add a new client
- Select qBittorrent
- Fill in a name, use `qbittorrent` as host, port `8888`, and the login for the web interface

#### Configuring Sonarr
- See `Configuring Radarr`

#### Configuring qBittorrent
You can leave this one alone, unless you want to change the login or download/seed settings.
