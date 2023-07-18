Post-work Check-list
====================

Standard checks
---------------

1. Any problems reported in **Site administration** → **Notifications**.
2. Any problems reported in **Site administration** → **Server** → **Environment**.
3. Check PHP settings: `max_execution_time` >= 300, `post_max_size` >= 256MB, `upload_max_filesize` >= 256 MB, `date.timezone` is set.
4. OPcache settings match [the Moodle recommendations](https://docs.moodle.org/402/en/OPcache#Configuration). May not be possible on shared hosting.
5. Check programs have been installed on the server if they’re specified in Moodle’s program path settings (for example, Ghostscript).
6. Check programs have been specified on Moodle's System paths page if they're available on the server (for example, `pathtophp`, `pathtodu`).
7. If Moodle has ClamAV enabled check this is installed.
8. Any themes installed and selected.
9. All additional plugins installed/upgraded as expected.
10. Log life time set to 1 year (confirm change with customer).
11. Setting **Use database for session information** is "No" (under **Site administration** → **Server** → **Session handling**).
12. Setting **Debug messages** is "NONE" (under **Site administration** → **Development** → **Debugging**).
13. Setting **Theme designer mode** is "No" (under **Site administration** → **Appearance** → **Theme settings**).
14. (Optional) Check Solr installed and configured.
15. Upgrading from Moodle <= 3.5: check if there are any assignments to be upgraded under **Site administration** → **Assignment upgrade helper**.
16. Cron set up correctly.
17. Maintenance mode has been disabled.
18. Any credentials supplied to customer, for example, site admin, database accounts.

Microsoft Windows-specific checks
---------------------------------

1. Copy CA bundle to Moodledata (see [SSL certificate for moodle.org](https://docs.moodle.org/en/SSL_certificate_for_moodle.org#Provide_the_CA_certificate_manually)).
2. (IIS) Check `system.webServer/handlers[name='PHP_via_FastCGI'].responseBufferLimit` is 0.
3. (IIS) Check `system.webServer/security/requestFiltering/requestLimits/maxAllowedContentLength` matches PHP settings `post_max_size` and `upload_max_filesize`.
4. (IIS) Check both `system.webServer/fastCgi/[fullPath='C:\PATH\TO\php-cgi.exe',arguments='']".activityTimeout` and `system.webServer/fastCgi/[fullPath='C:\PATH\TO\php-cgi.exe',arguments='']".requestTimeout` match PHP setting `max_execution_time`.
5. (IIS) Check PHP temporary files are being deleted after file upload.

Candidate checks
----------------

1. Enable and configure [X-sendfile](https://docs.moodle.org/en/Performance_recommendations#X-Sendfile) if available.
2. Run `admin/cli/mysql_compressed_rows.php` (upgrade and migration only).

------------------------------------------------------------------------------
Text is available under the [Creative Commons Attribution-ShareAlike License 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
