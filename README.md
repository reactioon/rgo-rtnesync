# (R) Package 

R Package is a set of tools created by Reactioon to connect the dots. The tools will work to enhance on reactioon a lot of aspects like high availability, fail over, data processing, analysis, and will improve reactioon to work with large amount of data and users. Offering the Reactioon Network a mix of web and standalone tools that will works online and offline.

# (R) Package / rtnesync

`rtnesync` is the package to sync data from exchanges to Reactioon. This will only work on machines to collect asset data at exchanges using the user computer resources, like internet, cpu and disk space. If you want, see below how to install it on your computer.

### Requirements

```
1. Reactioon Account
2. Reactioon Node License
3. PC with Debian 11 or CentOS 7 installed.
```
**Note:**  
The `license` of node can be get with `RTN` inside of `Network` in your `Reactioon Account`, and you need the knowledge of your system (linux, osx, windows) to manage the node.

By default `RTNSYNC` is part of (R) Package and it will use the `reactioon` folder inside of your OS (linux,osx,windows).   

`RTNESYNC` does not require any aditional software and is projected to any level of user.

## How To Install

The process to install RTNESYNC on your computer is easy, but reactioon folders is required.

```
cd /
mkdir /reactioon
cd /reactioon
mkdir logs
```

After execute the command above you will have an directory in the path `/reactioon` with a subfolder called `logs`.

**Note:** Reactioon folder will be used by all tools of (R) Package, not only by RTNESYNC.

#### Linux

To install `RTNESYNC` on your linux nothing needs to be installed, and the process is too easy. check the steps below:

**1. Download the package** 

```
cd ~
wget https://github.com/reactioon/rgo-rtnesync/raw/master/builds/rtnesync-unix
```

**2. Run installer**

Get network interface associated with your network interface
```
ifconfig
```

Go to user folder and set `uid` and `iface` to run the installer.
```
cd ~
./rtnesync-unix -install=yes -install-os=linux-debian11 -uid={UID OF NODE} -iface=eth0
```
**Note:** If you want install on Centos7, just change the `-install-os` to `linux-centos7`.

**3. Start service**

```
systemctl start rtnesync.service
```
**Note:** After reboot your machine the service will auto start, to disable it, use disable on systemctl `systemctl disable rtnesync.service`

### OSX

```
coming soon...
```

### Windows

```
coming soon...
```

## Properties

To change behaviour of your RTNESYNC you can use aditional properties, see the list below:

| Property | Default Value | Options | Description |
| --- | --- | --- | --- |
| -uid |  | --- | Unique ID of node. | 
| -host | rtp.reactioon.com | --- | Address of Reactioon Transport Network. | 
| -protocol | wss | ws|wss | protocol to transport data | 
| -iface | eth0 | * | ethernet network interface | 
| --- | --- | --- | --- |
| -install | no | yes|no | trigger to install binaries | 
| -install-os |  | linux-debian11|linux-centos7 | OS to install | 
| --- | --- | --- | --- |
| -app | rtnesync | * | app name for the binaries. | 
| -logs-limit | 100 | * | limit of lines inside of log file | 
| -daemon | no | yes|no | start the service with always running | 
| -version | --- | --- | show the version of rtnesync | 
| -test | no | --- | test routines to check integrity of data, binaries and machine resources. | 


**Note:** All properties can be changed, becareful while is using it.

## Logs

RTNESYNC use the logs folder to store data about processing and errors, you can see two files about RTNESYNC inside of logs folder.

```
cd /reactioon/logs
tail -f rtnesync.log
tail -f rtnesync_err.log
```
*Note:* The logs will store an limit number of lines, to increase set in flag.

## Tests

To run tests you will need inform the file with test data, if file don't exists, they will be created on first run with latest tests covered.

```
rtnesync -test=/reactioon/rtnesync_test.txt
```

After run the test command, all initial tests needs to be passed and nothing can be failed. If any of tests not pass, your machine will experience some problem while run this tool, on this case contact us in our community group. Check the expected result below

```
(a lot of details about each test will show before)
...

Resume:
10 Tests executed.
10 Tests passed.
0 Tests failed.

```
*Alert:* The total of tests is subjective, only to explain how the results will be.

That's all!  
The future is now!

---

@author José Wilker <josewilker@reactioon.com>