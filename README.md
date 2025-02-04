# Zabbix Template for TrueNAS SCALE rsync tasks monitoring

## Overview
For Zabbix version: 7.0 and higher. Can be easily backported to any earlier version.

SSH is using for TrueNAS rsync tasks monitoring. 
![Rsync tasks](https://github.com/user-attachments/assets/64aa29ea-8429-46d1-a668-6d99596e51ed)


This template is developed for monitoring state of TrueNAS SCALE rsync tasks:
* Monitor state
* Error messages
* Duration


LLD using for tasks discovery.

This template was tested on:

TrueNAS SCALE
* Version: 24.10

## Setup
SSH service should be enabled:

![Services](https://github.com/user-attachments/assets/5de2e67a-bdc3-4bb0-8f63-e08c6e9766c3)


![SSH](https://github.com/user-attachments/assets/fd67fe9e-9542-40e9-b21f-6c30a44dd184)


SSH user should be able to connect via SSH from the Zabbix Server.

![Users](https://github.com/user-attachments/assets/f0927d5c-8ce6-4512-8fde-7333ea951fc3)

![User settings](https://github.com/user-attachments/assets/61b917d6-ab74-4908-8b8b-ac51bd9a8402)

![Allow ssh login](https://github.com/user-attachments/assets/ba665495-3817-4f65-a9f1-cf425129e3d1)

Rsync task should have proper Description

![Task description](https://github.com/user-attachments/assets/c105174e-396a-4d0a-8281-9e5d2f9b8f5e)



## Author

Aleksey Volodin

## Macros used

Default macros values should be adjusted according your environment.

|Macro|Value|Description|
|-----|-----|-----|
|{$TRUENAS.SSH.PASS}||SSH user password.|
|{$TRUENAS.SSH.USER}|root|SSH user.|

## Template links

There are no template links in this template.

## Discovery rules

|Name|Description|Type|Key and additional info|
|----|-----------|----|----|
|TrueNAS rsync tasks dicovery|Discover all TrueNAS rsync tasks|SSH Agent|ssh.run[rsync.tasks.discovery]|

## Items collected

* rsync task state
* rsync error message
* rsync human readable description
* rsync duration time

## Triggers

* rsync task is failed
