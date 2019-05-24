

# Welcome (I'm talking to myself) Note : appname = replace it with name of your app.

## Installation
Create new app

```
heroku create appname -b https://github.com/infinitycr4k3r/elseclone.git
heroku git:clone -a appname
```

Existing app, use: `add|set`

```
heroku buildpacks:set https://github.com/infinitycr4k3r/elseclone.git -a appname
```

go to `appname` directory, create or copy `rclone.conf` and winrar registraton key `.rarreg.key` (optional) then commit the change

```
cd appname
git add .
git commit -am "add config"
git push heroku master
```
Get the rclone.conf and put it in the app folder appname.

## Usage
**Open remote Heroku**
```
cd appname
heroku run bash
# or
heroku run --app appname bash
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
