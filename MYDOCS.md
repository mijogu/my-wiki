# My WordPress Startup Manual

https://deliciousbrains.com/automating-local-wordpress-site-setup-scripts-part-3-automating-rest/


## Plugins

advanced-custom-fields-pro
advanced-forms-pro
acf-extended
advanced-forms
advanced-custom-fields-wpcli
user-menus
user-switching
wp-mail-logging
admin-columns


## WP CLI

Commands https://developer.wordpress.org/cli/commands/

ACF WPCLI (plugin)
Admin Command 

### New WP Installation

wp core install

wp config list
wp config create --dbname= --dbuser= --dbpass= --dbhost= --dbprefix=

Couldn't get the `--extra-php` flag working.

 --extra-php <<PHP 
//define('WP_DEBUG', true);
//define('WP_DEBUG_LOG', true);
//define( 'WP_HOME', '' );
//define( 'WP_SITEURL', '' );
//define('SENDGRID_API_KEY', '');`
//define('WP_MAILCATCHER', true);
PHP

wp db create 

(Generate random string https://www.random.org/strings/)

wp core install --url=jawngames.local --title="Jawn Games" --admin_user=jawngamemaster --admin_password=C3wGahuUEivPRgm --admin_email=mike@darngood.io

(To install in remote location -- or in a Docker)
--ssh=[<scheme>:][<user>@]<host\|container>[:<port>][<path>]

wp theme search understrap
wp theme install understrap 

git clone https://github.com/understrap/understrap-child.git wp-content/themes/understrap-child
rm -R wp-content/themes/understrap-child/.git*

wp theme activate understrap-child

## Database / WP Core

wp core update

wp cron

wp db export
wp db import
wp db query < debug.sql (Runs SQL commands from file)

wp export
wp import

## Scaffold

wp scaffold post-type  https://developer.wordpress.org/cli/commands/scaffold/post-type/
wp scaffold child-theme
wp scaffold plugin

Build a PHP script to run locally.
wp eval-file filename --skip-wordpress

## Themes 

wp theme search understrap
wp theme install understrap 
wp theme activate understrap(_child)

# Users 

wp user create {userlogin} {useremail} --user_pass= --first_name= --last_name= --send-email
wp user list --file=ID
wp user import-csv users.csv --send-email --skip-update
wp user term
wp user check-password 

## Menus

wp menu create "Main main"
wp menu item add-post {menuID} --title= --link= --target= --classes=
wp menu item list {menuID}

### Posts / Custom Post Types

wp post create --post_type=post --post_title='a sample post'
wp post generate --count= --post_type= --post_title= --post_content= 

wp post meta add
wp post meta update 

wp scaffold taxonomy {slug} --post_types= --label= > filename.php
wp taxonomy list 
wp term create category Apple --description="A fruit"


### ACF plugin

**Install plugin**
git clone https://github.com/hoppinger/advanced-custom-fields-wpcli.git wp-content/plugins/advanced-custom-fields-wpcli
wp plugin activate advanced-custom-fields-wpcli

**Unzip locally saved plugin**
unzip ~/Development/resources\ wordpress/advanced-custom-fields-pro.zip -d wp-content/plugins/advanced-custom-fields-pro

-d allows to be unzipped in another directory
or unzip in place and use mv


### Mailcatcher
mailcatcher


## Documentation

body class
disable admin header

change /uploads folder
change wp-login.php url


## Command Line / ZSH

http://zsh.sourceforge.net/

mkdir
cd
diff
date
cal

mv
Use mv to rename files.


cp
cp -a /source/. /dest/

pwd (tells you where you are)

create file(s)
touch .gitignore
touch file1.txt file2.txt file3.txt

foreach loop
for x in 1 2 3; do echo $x; done
for x in twentyseventeen twentytwenty; do wp theme delete $x; done

Use trash instead of rm, will send to Trash Can
trash file.txt file2.txt

Force reload .zshrc after changes.
source ~/.zshrc

MAMP Aliases (defined in .zshrc)ps
startmamp
stopmamp

alias startmamp='open /Applications/MAMP\ PRO.app; /Applications/MAMP/bin/start.sh' 
alias stopmamp='/Applications/MAMP/bin/stop.sh'

Get list of running processes, and PIPE that thru Regex search. 
Then use the appid to kill program. 
ps = Process Status
ps aux | grep MAMP
sudo kill {xxxxx}

pgrep {programname}
pkill {programname}

Print PHP info, and PIPE that thru searching for php.ini filepath.
php -i | grep php.ini

Open file with VS Code
code filename

Use file as input
command < file

Create file from output
command > file

Append to a file
command >> file

Run process in background
command &

Place a running process in the background.
<control>z 
then enter
bg 
(or enter fg to bring back)

find . -name "pattern" -print

man command (show manual for command)

cat (concatenate)
cat filename filename2 (displays contents of file(s))
cat -n filename (with line numbers)

Make file executable
chmod +x ~/Scripts/config.sh

## TODO

Run php file to query WP and save results to file

Close Mailcatcher chrome tab? 
https://unix.stackexchange.com/questions/237626/is-there-a-way-to-activate-a-particular-tab-of-chrome-via-bash

Send emails from Mailcatcher with Google? 
https://sites.google.com/site/mamppro/en/mamp-pro/server/postfix/working-configuration-for-some-isps/google

Try using Positional Arguments in PIPE functions
$0 $1 $2

Try MAMP startup script in Pastebin

Get multiple SSH keys working for git@git.wpengine.com

Get Magic WP No-Password links working.

Commands to look up:
tail
fsck "file system consistency check"
top

