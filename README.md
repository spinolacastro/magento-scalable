magento-scalable
================

Magento Store with scalability

This git repository creates a Magento installation on OpenShift.

Running on Getupcloud
----------------------------

Create an account at http://openshift.redhat.com/

Create a php-5.5 + mysql 5.1 application based on this repo's code (you can call your application whatever you want)

 rhc app create $appname php-5.5 mysql-5.1 --from-code=https://github.com/getupcloud/magento-scalable -s

Add Redis Cartridge to your application

  rhc add-cartridge http://cartreflect-claytondev.rhcloud.com/reflect?github=smarterclayton/openshift-redis-cart -a $appname

SSH into your application, copy the content of local.xml and add it to your local repo
	
   cat ${OPENSHIFT_REPO_DIR}php/app/etc/local.xml




Enable Storage Configuration Media
	Go to System -> Configuration 
		Menu Avanced -> System

	On  Storage Configuration for Media change to "Database", click on Synchronize and then "Save Config"





Don't Forget to check all settings on

 * System > My Account
 * System > Configuration > General > Countries Options
 * System > Configuration > General > Locale Options
 * System > Configuration > Admin
 * System > Configuration > System
 * System -> Cache Management
 * System -> Index Management
 