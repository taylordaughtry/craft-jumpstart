![JumpStart](http://i.imgur.com/xmZfxwz.png)

# JumpStart

JumpStart is a well-structured starter package for plugin development. It
assumes you're working with Craft 2.5. (Earlier versions won't have access to
some of the Craft's newer features for plugins, like changelogs.)

# Usage

`git clone` the repo into your `craft/plugins` directory, then start building!

If you rename your plugin immediately, be sure to rename your folder directory
and any files inside so Craft can see them and associate them with your plugin.

# Config or Settings?

There's a little confusion for plugin developers about which one to use. The
truth  is that there's a benefit to using both. If you're building an extensive
plugin  that needs to do different things in different environments, you should
go with a  config file. If your plugin's relatively small, using Craft's built-
in plugin settings is fine.

Remember that the user likely won't have the tech skills to reach a config file
in your plugin, so make sure any settings you place in it aren't critical to
your plugin's administration.

Use a config file if:
- The setting needs to be different in each environment
- Needs to be set dynamically via PHP
- Needs to be version-controlled

Use Plugin Settings if:
 - You need this setting to be easily updated by administrators
 - You need the setting to be validated
 - You need your plugin to run code when a setting's value changes.

Also, remember that config files are completely optional; you don't need them to
make a completely valid plugin.

### Retrieving and Overwriting Values

You can retrieve values from your plugin's config file like this:

`$configSettingValue = craft()->config->get('firstSample', 'jumpstart');`

Your config's values can be overriden by end-users by placing a file with your
plugin's name in their craft/config/ directory, ie:
`craft/config/jumpstart.php`


# Icons

If you'd like to use an icon for your plugin, update the `icon.svg` file in
`jumpstart/resources`. If your plugin will have its own CP tab, you'll need to
also update the `icon-mask.svg`.
