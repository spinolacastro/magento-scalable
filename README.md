magento-scalable
================

Magento Store with Scalability

This git repository creates a Magento installation on OpenShift.

Running on Getupcloud
----------------------------

Create an account at http://getupcloud.com/

Create a php-5.5 + mysql 5.1 application based on this repo's code (you can call your application whatever you want)

 rhc app create $appname php-5.5 mysql-5.1 http://cartreflect-claytondev.rhcloud.com/reflect?github=smarterclayton/openshift-redis-cart --from-code=https://github.com/getupcloud/magento-scalable -s


### Post-installation details


Enable Storage Configuration Media
	Go to System -> Configuration 
		Menu Advanced -> System
	On Storage Configuration for Media change to "Database", click on Synchronize and then "Save Config"



Don't Forget to check all settings on

 * System > My Account
 * System > Configuration > General > Countries Options
 * System > Configuration > General > Locale Options
 * System > Configuration > Admin
 * System > Configuration > System
 * System > Cache Management
 * System > Index Management
 