Cisco Packet Tracer Flatpak'ed
==============================
with Freedesktop runtime.

The Software License Agreement of Cisco Packet Tracer forbids the distribution
of the software, that means, no one can supply the full package but the manifest
file for flatpak building. It's easy, just follow the steps below.

## Clone this repo
`$ git clone https://github.com/rpallai/flatpak-pt.git`

## Install flatpak-builder
`$ sudo dnf install flatpak-builder`

## Download "Packet Tracer 7.1.1 for Linux 64 bit.tar.gz"
You can download from https://netacad.com after login. Put the file into the
"flatpak-pt" folder next to the .json manifest.

## Build and install the flatpak application
```
$ cd flatpak-pt
$ flatpak-builder --user --install build-dir com.cisco.PacketTracer-71.json
```

The build ends with the following lines if everything went well:
```
Installing for user: com.cisco.PacketTracer-71/x86_64/master from com.cisco.PacketTracer-71-origin
[####################] 2 metadata, 1 content objects imported
Now at e97c4c055a16.
Pruning cache
```

Now you can run the app from the Application Launcher, just search for "cisco".

## Set the "PT7HOME" enviroment variable
This extra step is required for the javaws applet used by web exams.

`$ echo "export PT7HOME=~/.local/share/flatpak/app/com.cisco.PacketTracer-71/current/active/files" >>~/.bashrc`

Log off and log in and that's all!