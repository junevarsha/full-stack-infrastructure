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

![ssh](https://drive.google.com/file/d/144z3LTUMzESE4n04w0r0hxeoG_tMsU6l/view?usp=sharing)

# 3. Bash and Nginx

# 4. Security

# 5. HTTP

# 6. Containers

# 7. Saving Data

# Resources

1. [Slides](jemyoung.com/fsfe)
2. [NotesBackup in drive](https://drive.google.com/file/d/1Qhhj8AoKurf92V7XYAaKqknC2QOKb0yD/view?usp=sharing)

