# Installing WordPress with WP-CLI

### Checking WP-CLI Version

Simply type this command to check the WP-CLI version information:

To install WP-CLI <a href="https://make.wordpress.org/cli/handbook/guides/installing/" target="_blank">click here</a>.

<code>wp --info</code>

Create directory

<code>cd /var/www/html</code>

<code>mkdir demo</code>

<code>wp core download</code>

<code>wp core config --dbname=db_gutenberg --dbuser=root --dbpass=mysql123 --dbhost=localhost --dbprefix=rl_ --extra-php <<PHP</code>

<code>define( 'WP_DEBUG_LOG', true );</code>

<code>PHP</code>

Use the following command for creating the database. Note that this command will create a fresh database with the name used in wp-config file.

<code>wp db create</code>

<code>wp core install --url="http://localhost/demo" --title="demo Test" --admin_user="admin" --admin_password="admin" --admin_email="test@test.com"</code>

Use the following command to Enable DEBUG and DEBUG LOG.

<code>wp config set WP_DEBUG true --raw</code>

<code>wp config set WP_DEBUG_LOG true --raw</code>

### To activate the theme, type:

<code>wp theme activate [theme name]</code>

### Display the WordPress version

<code>wp core version</code>

### Updating the WordPress core files:

<code>wp core update</code>

### To install a plugin, type the following command.

<code>wp plugin install [plugin name]</code>

### To update all themes

<code>wp theme update --all</code>

### To update all plugins

<code>wp plugin update --all</code>

### Reinstall WordPress Core

<code>wp core download --skip-content --force</code>

# Database

### Check database.

<code>wp db check</code>

### Create a new database.

<code>wp db create</code>

### Drop an existing database.

<code>wp db drop --yes</code>

### Reset the current database.

<code>wp db reset --yes</code>

### Delete all tables that match the current site prefix.

<code>wp db clean --yes</code>

### Export database

<code>wp db export</code>

### Export certain tables</code>

<code>wp db export --tables=wp_options,wp_users</code>

### Import MySQL from a file.

<code>wp db import wordpress_dbase.sql</code>

### Displays the database table prefix.

<code>wp db prefix</code>

### Repairs the database.

<code>wp db repair</code>

### Executes a SQL query against the database. Execute a query stored in a file

<code>wp db query < debug.sql</code>

### Check all tables in the database

<code>wp db query "CHECK TABLE $(wp db tables | paste -s -d, -);"</code>

### Displays the database name and size.

<code>wp db size</code>


# WordPress Menus

### Create a new menu

<code>wp menu create "My Menu"</code>

### List existing menus

<code>wp menu list</code>

### Create a new menu link item

<code>wp menu item add-custom my-menu Apple http://apple.com --porcelain
1922</code>

### Assign the 'my-menu' menu to the 'primary' location

<code>wp menu location assign my-menu primary</code>

### Deletes one or more menus.

<code>wp menu delete "My Menu"</code>

# Database Search And Replace

<code>wp search-replace 'http://example.dev' 'http://example.com' --precise --recurse-objects --all-tables</code>


# Regenerating Thumbnails

### Regenerating All Thumbnails
To regenerate all thumbnails for all images inside your WordPress media library, you can use the following command:

<code>wp media regenerate --yes</code>

### Regenerating Missing Thumbnails
You can regenerate thumbnails for only the missing image sizes using the --only-missing option like this:

<code>wp media regenerate --only-missing</code>

### Regenerating Thumbnails for Specific Images
If you want to regenerate thumbnails for a specific image, you can specify it by including the attachment ID after the command like this:

<code>wp media regenerate 122</code>

To regenerate thumbnails for multiple specified attachment IDs, just add them to the command like the following example:

<code>wp media regenerate 125 234 456</code>

### Keeping Old Thumbnail Sizes
When regenerating your WordPress media library image thumbnails, the default behavior is to delete the old thumbnails. If you want to keep them, you can use the --skip-delete option:

<code>wp media regenerate --skip-delete</code>

### Regenerating Specific Thumbnail Sizes

<code>wp media regenerate --image_size=large</code>

### List all registered image sizes

<code>wp media image-size</code>

# Maintenance Mode

### Activating Maintenance Mode
<code>wp maintenance-mode activate</code>

### Deactivate Maintenance Mode
<code>wp maintenance-mode deactivate</code>

### Display Maintenance mode status.
<code>wp maintenance-mode status</code>

### Get Maintenance mode status for scripting purpose.
<code>wp maintenance-mode is-active</code>

# Importing WordPress Content

### Importing WordPress WXR (.xml) Files
<code>wp import my-file.xml</code>

### Importing WordPress WXR (.xml) Files
<code>wp import my-file.xml</code>

### Creating Non-Existent Authors
If you want to create any authors that don't already exist, set value of the --authors option to create like this:

<code>wp import my-file.xml --authors=create</code>

### Skipping Non-Existent Authors
If you'd like to just leave the post's author empty if the user doesn't already exist, you can set the value of the --authors option to skip:

<code>wp import my-file.xml --authors=skip</code>

### Skipping Attachment Imports
<code>wp import my-file.xml --skip=attachment</code>

### Skipping Thumbnail Generation
<code>wp import my-file.xml --skip=image_resize</code>

# Exporting WordPress Content

### Exporting All WordPress Content
<code>wp export</code>

### Changing Your Export File Path
<code>wp export --dir="/my/path/here"</code>

### Exporting Without Comments
<code>wp export --skip_comments</code>

# WordPress All Cron

### Displaying All Cron Events
<code>wp cron event list</code>

### Running All WordPress Cron Events
If you want to trigger all currently due cron events (events that are due but haven't been run yet), you can run them with the following command:

<code>wp cron event run --due-now</code>

# WordPress cache flush

### Manually Clearing the Object Cache with WP-CLI
<code>wp cache flush</code>

# WordPress Transient

### Transients deleted from the database
<code>wp transient delete --all</code>

# WordPress search and replace in DB

<code>wp search-replace 'old.example.com' 'new.example.com'</code>

# Searching All Database Tables

<code>wp db search 'my search string'</code>

### Searching Through Specific Tables
<code>wp db search 'my search string' wp_posts</code>

# WordPress Core Language Packs

### Listing Available Language Packs
To view a list of all language packs that can be installed with WP-CLI, simply use the following command:

<code>wp language core list</code>

### Listing Installed Language Packs
To get a list of the currently installed language packs for WordPress core, issue the following WP-CLI command:

<code>wp language core list --status=installed</code>


### Installing a Language Pack
To install a language pack for WordPress core, just grab the language name (the list command helps with this) and install it using the install subcommand like this:

<code>wp language core install es_ES</code>

### Activating a Language Pack
<code>wp language core activate es_ES</code>

### Uninstalling a Language Pack
<code>wp language core uninstall es_ES</code>

### Updating All Language Packs
<code>wp language core update</code>

### Create POT file for theme and plugin

<code>wp i18n make-pot /var/www/html/demo/wp-content/themes/hello-world/ /var/www/html/demo/wp-content/themes/hello-world/languages/hello-world.pot</code>

<code>wp i18n make-pot /var/www/html/demo/wp-content/plugins/hello-world-addons/ /var/www/html/demo/wp-content/plugins/hello-world-addons/languages/hello-world-addons.pot</code>


# WordPress Plugin


### Activate plugin

<code>wp plugin activate hello</code>

### Deactivate plugin

<code>wp plugin deactivate hello</code>

### To deactivate all your plugins at once run the following command.

<code>wp plugin deactivate --all</code>

### Delete plugin

<code>wp plugin delete hello</code>

### Install the latest version from wordpress.org and activate

<code>wp plugin install bbpress --activate</code>

### List active plugins on the site.

<code>wp plugin list --status=active --format=json</code>
 
### Uninstalls one or more plugins.

<code>wp plugin uninstall hello</code>

### Updates one or more plugins for development version.

<code>wp plugin update bbpress --version=dev</code>

### Update all plugins

<code>wp plugin update --all</code>

### Update all plugins except akismet

<code>wp plugin update --all --exclude=akismet</code>

### You can also install older versions of WordPress plugins if needed with the --version attribute.

<code>wp plugin install wordpress-seo --version=4.8 --activate</code>
