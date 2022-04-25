# My WordPress Startup Manual

https://deliciousbrains.com/automating-local-wordpress-site-setup-scripts-part-3-automating-rest/


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



# Terminus

