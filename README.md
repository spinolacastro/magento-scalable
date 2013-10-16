Scalable Magento on GetupCloud
================

Magento Store with Scalability

This git repository creates a Magento installation on OpenShift.

Running on Getupcloud
----------------------------

Create an account at http://getupcloud.com/

Create a php-5.5 + mysql 5.1 application based on this repo's code (you can call your application whatever you want)

	$ rhc app create $appname php-5.5 mysql-5.1 http://cartreflect-claytondev.rhcloud.com/reflect?github=smarterclayton/openshift-redis-cart --from-code=https://github.com/getupcloud/magento-scalable -s

That's it, you can access your scalable Mangento at:
	
	http://$appname-namespace.getup.io/
	
Default admin credentials: username _admin_ password _OpenShiftAdmin123_.

### Post-installation details

####Change Secret Key

For security reasons you should change the default secret key at _php/app/etc/local.xml.erb_ of your local repo:

To generate a new secret key:

	$ openssl rand -base64 33
	
Paste the result at line 83 of _local.xml.erb_ file, commit and push
	

After the installation it is important to change the admin password and other Magento configurations properly. Log in to

	http://$appname-$yournamespace.rhcloud.com/admin
	
####Enable Storage Configuration Media

Go to System -> Configuration -> Menu Advanced -> System

On Storage Configuration for Media change to "Database", click on Synchronize and then "Save Config"


### Important!!

Don't Forget to check all settings on

 * System > Cache Management
 * System > Index Management
 * System > My Account
 * System > Configuration > General > Countries Options
 * System > Configuration > General > Locale Options
 * System > Configuration > Admin
 * System > Configuration > System
 
 
