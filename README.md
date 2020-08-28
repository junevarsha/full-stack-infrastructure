# 1. Introduction

Full Stack: someone who can build application from start -> finish

Command Line: Not all servers have GUIs. GUI is not powerful enough

Shell: Command interpreter to interface with system

Terminal: Runs shell applications

Shell -> application -> Kernel

## Understanding the internet

A system of globally interconnected devices. Computers talk to each other.

Private Internet - Intranet

## How does the internet work?

IP Address: label assigned to internet connected device
(IPV4/IPV6)

TCP - lossless (HEY(SYN) ACK...)

UDP - one way dataflow (hey and i assume you heard me)

PING - just does HEY HEY HEY

## Domain Name System

Trust system - ICANN - you pay to icann - internet phone book

DNS - closest server will resolve the domain name to ip Address

Subdomain vs path - subdomain means different site(partition) - path is just another route

Nameservers - actual entity that keeps the domain to ip address mapping.

    > Varsha just got espressoandcroissant.com - its not pointing anywhere but if
    you wanna look it up, I know exactly where it is.
    (namesevers - record keepers of the internet)

ping and traceroute - ICMP - health checks

some sites deny ping - blackholing - just like a cool person ignoring you at a party

Packet - smallest bit of information
like envelop - basic info - contains metadata

tcp - error correcting

udp - just broadcasting data, faster(like kupa)

Net neutrality - my understanding is it is kind of like bribing for internet?

EVERYTHING RUNS ON TRUST

# 2. Server Setup

## What does server do?

Serves Content see server.js (simple server)

Data centers(collection of computers) - fraction of server

Cloud - goal is to get least number of hops - we can keep multiple copies of data in various places - renewable energy - wind farm - elastic - scale up & down - pay for what you need - on-demand

server is divided into chunks. chunks - virtual private server
(process isolation, chunks dont know about each other)

Lets buy VPS in digital ocean.

## Operating Systems

Why do we choose Ubuntu?

Windows and Unix

Linux is flavor of Unix

Kernel - talks to machine hardware

Cool Idea behind Linux:
Instead of baking everything to OS
we bake Utilities

Utilities -> applications that just do one thing

Long Term Support (LTS version)

For production - always use LTS.
Netflix uses LTS node. Downside is if node supports top-lvl asynch await 
we cant use it until it moves to LTS node.

## SSH

    ssh -i fsfe root@<ip>
    <add fsfe to keychain if not added>
    ssh root@<ip> -v

## AWS->Digital Ocean NS transfer

#is - super user
check whoami

a records = map name to ip address
cname = maps name to name

every ubuntu distr. should have auth log

registrar = aws
Nameservers in route 53
replace it with digital ocean 
NS records

This means we moved ownership of who
owns espressoandcroissant.com to
digital ocean.

## Server Setup

Update software, create new user & su
Enable login, disable root login

    apt update
    apt upgrade
    adduser varsha
    usermod -aG sudo varsha
    su varsha
    sudo cat /var/log/auth.log
    ssh -i fsfe root@<ip>
    sudo head less /var/log/auth.log
    sudo tail less /var/log/auth.log
    sudo tail -f less /var/log/auth.log
    mkdir -p ~/.ssh
    vi ~/.ssh/authorized_keys
    chmod 644 ~/.ssh/authorized_keys
    sudo vi /etc/ssh/sshd_config
    sudo service sshd restart

### Nginx and node app setup with version control

### Intro

Web server,light weight, extremely fast

It can do little bit of everything...

Apache - most popular

LAMP stack - Linux, apache, mysql, php

### Recap - HOW DOES THE INTERNET WORK?

domain-> ns-> i know wr ur trying to go -> 
here is the IP -> switch/router/nodes ->server
-> nginx -> html page


    sudo apt install nginx
    yes
    sudo service nginx start
    sudo less /etc/nginx/sites-available/default
    sudo vi /var/www/html/index.html

### Node

js environment for server side

binding for the v8 enginer(google) developed
for chrome (most popular compiler)

single threaded js engine that execultes js 
handles requests

    sudo apt install nodejs npm
    sudo apt install git
    echo $USER
    sudo chown -R $USER:$USER /var/www
    mkdir /var/www/app
    cd /var/www/app/
    git init
    mkdir -p ui/js ui/css ui/html

    touch app.js
    npm init
    npm i express --save
    cat package.json
    vi app.js (add express hello world)
    node app.js
    sudo vi /etc/nginx/sites-available/default
    sudo service nginx reload
    node app.js

### Process manager

services - highest level cmnd for any sort of 
daemon running in the background
    simple wrapper
    systemctl - more advanced

process manager - keeps your app running
handle errors

    nginx -t
    node app.js
    sudo npm -i g pm2
    sudo npm i -g pm2
    pm2 start app.js
    pm2 startup

### Version control with Git

    cd ~/.ssh/
    ssh-keygen
    cat id_rsa.pub
    cd /var/www/app/
    git remote add origin git@github.com:junevarsha/full-stack-demo.git
    git remote -v
    git pull
    git add .
    git commit -am "simple express setup"
    git push -u origin master

## Recap

fail2ban
express performance tips

a lot of unappreciated work

domain -> IP -> server
-> web server -> application server

# 3. Bash and Nginx

## Bash

    touch test.log
    ps > test.log
    cat test.log
    ls /var/log
    find /var/log/ -name sys
    sudo find /var/log/nginx/ -type f -name "*.log"
    find / -type d -name log
    sudo find / -type d -name log
    ps aux | grep node
    sudo cat /var/log/auth.log
    sudo cat /var/log/auth.log | grep varsha

## Nginx

jack of all trades

redirect is really powerful

301 vs 302 - perm vs temp

use temp. redirect for minor errors like
products missing in product page
so when crawlers come back and check
they index your pages

:: - ipv6 notation

[Difference-between-lossy-compression-and-lossless-compression](https://www.geeksforgeeks.org/difference-between-lossy-compression-and-lossless-compression/)

Nginx - gzip

compression stuff - very powerful

# 4. Security

# 5. HTTP

# 6. Containers

# 7. Saving Data

# Resources

1. [Slides](jemyoung.com/fsfe)
2. [NotesBackup in drive](https://drive.google.com/file/d/1Qhhj8AoKurf92V7XYAaKqknC2QOKb0yD/view?usp=sharing)

