# Heroku SRB2Kart Server
Runs a Free [SRB2Kart](https://github.com/STJr/Kart-Public) Server within Heroku.

## Features

* Compatible with Addons (Place Addons in the base folder, load them in `kartserv.cfg`)

## Notes

* Due to Heroku limitations, this Server cannot be advertised on the Master Server
* Due to SRB2Kart limitations, Dynu DNS (SRV DNS Records) is not supported

## Setup

### Heroku Git Remote

First, clone this Repo

```
git clone https://github.com/Epicfisher/heroku-srb2kart-server
```

Next, create a Heroku app, and then link your Repo to use Heroku as your Remote using the [CLI](https://toolbelt.heroku.com/)

```
heroku git:remote -a <Your-App-Name>
```

You can now Freely Edit the Server Config/Add Addons etc.

### LocalToNet (Creates a Temporary Joinable IP Address for your Server)

Create a New [Free LocalToNet Account](https://localtonet.com/) and copy your Auth Token

Set the `LOCALTONET_API_TOKEN` Config Variable to your Auth Token

```
heroku config:set LOCALTONET_API_TOKEN="Your-Auth-Token"
```

Navigate to the [TCP/UDP Page](https://localtonet.com/tunnel/tcpudp) and Create a Tunnel with the Following Information set. All other Fields can be Left as Default

```
Protocol Type = UDP
Server = (Pick the Server Closest to you)
Port = 5029
```

### Upload the Server

Finally, Commit & Push the Repo to Heroku

```
git add .
git commit -am "Heroku Initial Upload"
git push heroku
```

## Usage

After Enabling your Worker/Web Dyno in the Resources tab, your Server should Start

If using **LocalToNet**, your Server's IP Address will be found at `https://localtonet.com/tunnel/tcpudp` 