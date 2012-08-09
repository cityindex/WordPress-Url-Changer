WordPress-Url-Changer
=====================

A command line utility to change the name of a WordPress site 

Scenario
--------

1. You have an existing WordPress site running at mysite.com
1. You have a test version of that site running at test.mysite.com
1. You grab the files & a MySQL database dump of the mysite.com, 
copy them into the site root of the test.mysite.com site and restore the database dump over the test.mysite.com DB.
1. You run ```wordpress-url-changer --new_name test.mysite.com``` at the SSH terminal of test.mysite.com
    * This changes any Url references in the relevant config files (eg, wp-config.php)
    * This changes any Url reference in the relevant DB tables
1. You can now load http://test.mysite.com in your browser, and see a mirror of the live site in every respect except that the urls are different.

Similar applications
--------------------
1. https://github.com/interconnectit/Search-Replace-DB/blob/filestream/searchreplacedb2.php claims to handle search and replace of serialised PHP variables in the DB
1. ServerPress has this functionality as part of the scrubbing process it employs during site import
1. Creating this as a plugin for [wpcli](https://github.com/wp-cli/wp-cli) might provide a useful starting point eg. a way to extract the DB settings variables from the wp-config.php