# Installing WordPress with WP-CLI

<h3>Checking WP-CLI Version</h3>

Simply type this command to check the WP-CLI version information:

To install WP-CLI <a href="https://make.wordpress.org/cli/handbook/guides/installing/" target="_blank">click here</a>.

<code>wp --info</code>

<code>wp core download</code>

<code>wp core install --url="http://localhost/demo"  --title="Demo" --admin_user="admin" --admin_password="admin" --admin_email="admin@admin.com"</code>

<code>wp core config --dbname=db_demo --dbuser=root --dbpass=mysql123 --dbhost=localhost --dbprefix=wp_</code>

<p>Use the following command for creating the database. Note that this command will create a fresh database with the name used in wp-config file.</p>

<code>wp db create</code>

<h3>To activate the theme, type:</h3>

<code>wp theme activate [theme name]</code>

<h3>Updating the WordPress core files:</h3>

<code>wp core update</code>

<h3>To install a plugin, type the following command.</h3>

<code>wp plugin install [plugin name]</code>

<h3>To update all themes</h3>

<code>wp theme update --all</code>

<h3>To update all plugins</h3>

<code>wp plugin update --all</code>

# Regenerating Thumbnails

<h3>Regenerating All Thumbnails</h3>
<p>To regenerate all thumbnails for all images inside your WordPress media library, you can use the following command:</p>
<code>wp media regenerate --yes</code>

<h3>Regenerating Missing Thumbnails</h3>
<p>You can regenerate thumbnails for only the missing image sizes using the --only-missing option like this:</p>
<code>wp media regenerate --only-missing</code>

<h3>Regenerating Thumbnails for Specific Images</h3>
<p>If you want to regenerate thumbnails for a specific image, you can specify it by including the attachment ID after the command like this:</p>
<code>wp media regenerate 122</code>

<p>To regenerate thumbnails for multiple specified attachment IDs, just add them to the command like the following example:</p>
<code>wp media regenerate 125 234 456</code>

<h3>Keeping Old Thumbnail Sizes</h3>
<p>When regenerating your WordPress media library image thumbnails, the default behavior is to delete the old thumbnails. If you want to keep them, you can use the --skip-delete option:</p>
<code>wp media regenerate --skip-delete</code>

<h3>Regenerating Specific Thumbnail Sizes</h3>
<code>wp media regenerate --image_size=large</code>

# Maintenance Mode

<h3>Activating Maintenance Mode</h3>
<code>wp maintenance-mode activate</code>

<h3>Deactivate Maintenance Mode</h3>
<code>wp maintenance-mode deactivate</code>

# Importing WordPress Content

<h3>Importing WordPress WXR (.xml) Files</h3>
<code>wp import my-file.xml</code>

<h3>Importing WordPress WXR (.xml) Files</h3>
<code>wp import my-file.xml</code>

<h3>Creating Non-Existent Authors</h3>
<p>If you want to create any authors that don't already exist, set value of the --authors option to create like this:</p>
<code>wp import my-file.xml --authors=create</code>

<h3>Skipping Non-Existent Authors</h3>
<p>If you'd like to just leave the post's author empty if the user doesn't already exist, you can set the value of the --authors option to skip:</p>
<code>wp import my-file.xml --authors=skip</code>

<h3>Skipping Attachment Imports</h3>
<code>wp import my-file.xml --skip=attachment</code>

<h3>Skipping Thumbnail Generation</h3>
<code>wp import my-file.xml --skip=image_resize</code>

# Exporting WordPress Content

<h3>Exporting All WordPress Content</h3>
<code>wp export</code>

<h3>Changing Your Export File Path</h3>
<code>wp export --dir="/my/path/here"</code>

<h3>Exporting Without Comments</h3>
<code>wp export --skip_comments</code>

# WordPress All Cron

<h3>Displaying All Cron Events</h3>
<code>wp cron event list</code>

<h3>Running All WordPress Cron Events</h3>
<p>If you want to trigger all currently due cron events (events that are due but haven't been run yet), you can run them with the following command:</p>
<code>wp cron event run --due-now</code>

# WordPress cache flush

<h3>Manually Clearing the Object Cache with WP-CLI</h3>
<code>wp cache flush</code>

# WordPress Transient

<h3>Transients deleted from the database</h3>
<code>wp transient delete --all</code>

# WordPress search and replace in DB

<code>wp search-replace 'old.example.com' 'new.example.com'</code>

# Searching All Database Tables

<code>wp db search 'my search string'</code>

<h3>Searching Through Specific Tables</h3>
<code>wp db search 'my search string' wp_posts</code>

# WordPress Core Language Packs

<h3>Listing Available Language Packs</h3>
<p>To view a list of all language packs that can be installed with WP-CLI, simply use the following command:</p>
<code>wp language core list</code>

<h3>Listing Installed Language Packs</h3>
<p>To get a list of the currently installed language packs for WordPress core, issue the following WP-CLI command:</p>
<code>wp language core list --status=installed</code>


<h3>Installing a Language Pack</h3>
<p>To install a language pack for WordPress core, just grab the language name (the list command helps with this) and install it using the install subcommand like this:</p>
<code>wp language core install es_ES</code>

<h3>Activating a Language Pack</h3>
<code>wp language core activate es_ES</code>

<h3>Uninstalling a Language Pack</h3>
<code>wp language core uninstall es_ES</code>

<h3>Updating All Language Packs</h3>
<code>wp language core update</code>

<h3>Create POT file for theme and plugin</h3>
<code>wp i18n make-pot /var/www/html/demo/wp-content/themes/hello-world/ /var/www/html/demo/wp-content/themes/hello-world/languages/hello-world.pot</code>

<code>wp i18n make-pot /var/www/html/demo/wp-content/plugins/hello-world-addons/ /var/www/html/demo/wp-content/plugins/hello-world-addons/languages/hello-world-addons.pot</code>
