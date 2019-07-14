

# Welcome (I'm talking to myself) Note : appname = replace it with name of your app.

## Installation
Fork this repo, add your rclone and winrar file in your repo, add the below buildpacks in your heroku app and then deploy your repo.

```
https://github.com/Infinitycr4k3r/elseclone.git
https://github.com/Infinitycr4k3r/ytdl.git
https://github.com/Infinitycr4k3r/ffmpeg.git
```

## Usage
**Open remote Heroku**
```
cd appname
heroku run bash
# or
heroku run -a appname bash
```

**Upload to Google Drive**

```
rclone copy /app/(file or folder) remote:/(folder or leave it blank? Your Wish) -P -v --transfers=1(change it and you'll be able to download specified no. of files at a time) --drive-acknowledge-abuse
```

**Upload from one Google Drive to another Google Drive**

```
rclone copy -vv --disable copy drive1:/ drive2:/ -P -v --drive-chunk-size 64M --drive-acknowledge-abuse --transfers=1
```

**view file on Google drive**
```
rclone lsd gdrive_config:remote_drive_dir
```
view option:

`lsd` only show file in current directory

`ls` show file including in subdirectory (recursvely)

**Download file using `Aria2`**

Aria2 is command-line download accelerator
```
aria2c -x4 http://host/file.rar
```
`-x4` mean download using 4 connection

**To extract `.rar` file**

to current directory
```
unrar e file.rar
```

with full path

```
unrar x file.rar
```
