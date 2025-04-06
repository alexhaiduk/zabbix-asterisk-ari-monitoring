# Zabbix Asterisk ARI monitoring (over http or https)
Asterisk ARI (RESTful API) template with discovery rule, panel, graphs and triggers.
The template gets Asterisk metrics from ARI by HTTP agent.
You should enable the mini-HTTP Server, add the option enabled=yes in the [general] section of the http.conf file and option enabled=yes in the [general]
section of the ari.conf file, further create Asterisk ARI user with read only
permissions within your Asterisk instance.
Please, define {$ARI.PROTOCOL}, {$ARI.PREFIX}, {$ARI.PORT} used in the http.conf.
Then you can define {$ARI.USERNAME} and {$ARI.SECRET} macros in the template for using on the host http access.
If there are errors, increase the logging to debug level and see the Zabbix server log.
Item for single endpoint monitoring is disabled by default.
Discovery rule set with macros.
***
Macroses:
 - {$ARI.PORT} Asterisk ARI port number (from http.conf).
 - {$ARI.PREFIX} Asterisk ARI (RESTful API) prefix (from http.conf).
 - {$ARI.PROTOCOL} Asterisk ARI use protocol (from http.conf, http or https).
 - {$ARI.REGEX.TRUNK} The regexp for the identification of trunk peers (for discovery filter rule, or use '.+' - for any).
 - {$ARI.REGEX.TRUNK.TECH} The regexp for the technology of trunk peers (for discovery filtr rule, or use '.+' - for any).
 - {$ARI.SECRET} The Asterisk ARI user password (from ari.conf).
 - {$ARI.TRUNK} Single name of the trunk for monitoring (default: disabled and NOT regexp)
 - {$ARI.TRUNK.TECH} Technology of the trunk for monitoring (default: disabled and NOT regexp)
 - {$ARI.USERNAME} The Asterisk ARI user name (from ari.conf).
***
