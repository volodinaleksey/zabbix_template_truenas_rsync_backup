# Zabbix Template for TrueNAS rsync tasks monitoring

## Overview
For Zabbix version: 7.0 and higher. Can be easily backported to any earlier version.

SSH is using for TrueNAS rsync tasks monitoring.
![image](https://github.com/user-attachments/assets/64aa29ea-8429-46d1-a668-6d99596e51ed)


This template is developed for monitoring state of TrueNAS rsync tasks:
* Monitor state


LLD using for tasks discovery.

This template was tested on:

Truenas SCALE
* Version: 24.10

## Setup
SSH service should be enabled:

![image](https://github.com/user-attachments/assets/a947453e-2c91-487b-9f0f-55fae99514bd)
![image](https://github.com/user-attachments/assets/d037fb23-daf2-4012-8843-632b34e92972)

Chousen user should be abble to connect vis SSH from Zabbix Server.
![image](https://github.com/user-attachments/assets/ddef53fd-fa88-4f3b-9472-803db78d77f1)
![image](https://github.com/user-attachments/assets/9b54a0b4-6645-42a1-832d-015879e55073)


## Author

Aleksey Volodin

## Macros used

Default macros values should be adjusted according your environment.

|Macro|Value|Description|
|-----|-----|-----|
|{$TRUENAS.SSH.PASS}||SSH user password.|
|{$TRUENAS.SSH.USER}||SSH user.|

## Template links

There are no template links in this template.

## Discovery rules

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|TrueNAS rsync tasks dicoveryy|Discover all TrueNAS rsync tasks|SSH Agent|ssh.run[rsync.tasks.discovery]|

## Items collected

* rsync task state

## Triggers

* rsync task is failed
