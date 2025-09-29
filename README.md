# rpi_pihole_selfmaint
A dockerized pihole installation on ubuntu core which is self maintaining

## Goals
The goal of this project was having a self maintaining installation of basic network services without the need of putting hands on it after installation.
I had tried several ideas to acheive this but I always had to do manual steps of either keeping software uptodate or changing conifgs or other stuff that I did not want to bother with.
I've tried to install pihole as a docker container on my unraid NAS. It worked sort of but I always had to do manual updates to the docker container when there was a new version.
Additionally I experienced a strange behavior resulting in DNS requests getting slower over time until they reached a point where a simple DNS request took 10s to be answered.
The strange part was it could not be diagnosed nor did I find a plausible reason for this. So I decided to give ubuntu core a try and I can say: I am happy now.

## Benefits
- No maintenance of OS (ubuntu core updates itself in a safe way)
- No maintenance of Docker containers (watchtower does this for me)
- Config is custumizable if needed
- Repeatable and stable setup (can be replicated in minutes)
- Fire and Forget

## Features
- A very fast DNS resolver locally run in your network
- Ad blocking based on DNS
- ipV6 ready (radvd and DNSmasq advertise the pihole as a DNS server in your network)

## Setup
- setup a RPI(4/5) with ubuntu core
- configure its network to a static address (make sure to also set the ipV6 address from the docker-compose.yml to your network interface if you want ipV6)
- sudo snap install docker
- create a directory where you want to have your files stored
- create the subdirectories and the config files I have prepared
- make changes if necesary
- sudo docker compose up docker-compose.yml

That's all. You now should have a running install of pihole with unbound root dns resolving.
