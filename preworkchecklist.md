Pre-work Check-list
===================

Note the following items:

1. Moodle version and build number (from **Site administration** > **Notifications** or `version.php`).
2. Any warnings on the Notifications page.
3. PHP version (from **Site administration** > **Server** > **PHP info**).
4. Source code directory, for example, from `$_SERVER['SCRIPT_FILENAME']` in **PHP info**.
5. Database type and version (from **Site administration** > **Server** > **Environment**, database row).
6. Note any warnings on the Environment page.
7. Compile list of installed additional plugins and their versions as listed under **Site administration** > **Plugins** > **Plugins overview**, **Additional plugins**.
8. Which themes are selected for all device types (from **Site administration** > **Appearance** > **Themes** > **Theme selector**):
    1. Default.
    2. Legacy.
    3. Mobile.
    4. Tablet.
9. Moodledata size, for example, with the command `du -sxh moodledata`.
10. Database size (for example, for MySQL/MariaDB: `SELECT ROUND(SUM(data_length + index_length) / 1024 / 1024, 1) size_mb FROM information_schema.tables WHERE table_schema = 'moodledb' GROUP BY table_schema`).
11. Which authentication plugins are enabled/configured. How many users are authenticated by non-standard ones. This is shown under **Site administration** > **Plugins** > **Authentication** > **Manage authentication**. There may be an obsolete authentication plugin enabled which would need removing for an upgrade, but we must check if there are any users authenticated by this.
