A custom module for [beverageuniverse.com](https://beverageuniverse.com) (Magento 2). 

## How to install
```
bin/magento maintenance:enable
rm -rf composer.lock
composer clear-cache
composer require beverageuniverse/core:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
bin/magento cache:enable
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Magento/Beverage \
	-f en_US
bin/magento maintenance:disable
```

## How to upgrade
### beverageuniverse.com
```
bin/magento maintenance:enable
composer --ignore-platform-reqs remove beverageuniverse/core
rm -rf composer.lock
composer clear-cache
composer --ignore-platform-reqs require beverageuniverse/core:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
bin/magento cache:enable
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Magento/Beverage \
	-f en_US
bin/magento maintenance:disable
```

### bu2.mage2.pro
```
bin/magento maintenance:enable
composer remove beverageuniverse/core
rm -rf composer.lock
composer clear-cache
composer require beverageuniverse/core:*
bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
bin/magento setup:di:compile
bin/magento cache:enable
rm -rf pub/static/*
bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US
bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Magento/Beverage \
	-f en_US
bin/magento maintenance:disable
```

### bu.mage2.pro
```
php7.1 bin/magento maintenance:enable
php7.1 /usr/local/bin/composer remove beverageuniverse/core
rm -rf composer.lock
php7.1 /usr/local/bin/composer clear-cache
php7.1 /usr/local/bin/composer require beverageuniverse/core:*
php7.1 bin/magento setup:upgrade
rm -rf var/di var/generation generated/code
php7.1 bin/magento setup:di:compile
php7.1 bin/magento cache:enable
rm -rf pub/static/*
php7.1 bin/magento setup:static-content:deploy \
	--area adminhtml \
	--theme Magento/backend \
	-f en_US
php7.1 bin/magento setup:static-content:deploy \
	--area frontend \
	--theme Magento/Beverage \
	-f en_US
php7.1 bin/magento maintenance:disable
```