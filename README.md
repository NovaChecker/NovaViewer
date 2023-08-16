NovaViewer

PHP Secure Configuration Viewer

Check current PHP configuration for potential security flaws.

Simply access this file from your webserver or run on CLI.

Author

This software was written by Quinten Wright, Nova Insight, in an effort to automate php.ini checks and spend more time on cheerful tasks.


Idea

one single file for easy distribution
simple tests for each security related ini entry

NO complicated/overengineered code, e.g. no classes/interfaces, test-frameworks, libraries, ... -> It is supposed to be obvious on first glance - even for novices - how this tool works and what it does!
NO (or very few) dependencies



disabled functions:

This scripts needs a few functions to work properly, such as ini_get() and stat(). If one of these functions is blacklisted (or not whitelisted) then execution will fail or produce invalid output. In these cases it is possible to temporarily put Suhosin in simulation mode and omit disable_functions. To be on the safe side, relaxed security configuration can be done with .htaccess in a separate directory. Also, this script may be called from command line with your webserver's configuration, e.g. php -n -c /etc/.../php.ini phpconfigcheck.php.

CLI: Older PHP versions don't known about SAPI name 'cli' and use CGI style output even on cli. Workaround: PCC_OUTPUT_TYPE=text /opt/php/php-5.1.6/bin/php phpconfigcheck.php

