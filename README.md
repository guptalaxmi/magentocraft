# magentocraft
magentocraft
follow this url for 
## Display Dynamic SKU on configurable product view Magento1
https://stackoverflow.com/questions/13444995/display-dynamic-sku-on-configurable-product-view-magento
file location: D:\xampp\htdocs\magento1.9\app\design\frontend\northgate\default\template\catalog\product\view\type\options

Magento2 issues:

Error: admin url not working

solution: Open up app/etc/di.xml find the path “Magento\Framework\App\View\Asset\MaterializationStrategy\Symlink” and replace to “Magento\Framework\App\View\Asset\MaterializationStrategy\Copy”
--------------------------------------

Error:  You did not sign in correctly or your account is temporarily disabled.

solution1: run command
php bin/magento admin:user:unlock admin
solution2:
In root \vendor\zendframework\zend-crypt\src\Utils.php 
and change in line 32
if (function_exists(‘hash_equals’)) { return hash_equals($expected, $actual); }
To
if (function_exists(‘hash_equals’)) { return true; }

----------------------------------------------------------------
Magento admin menu not working:

app/etc/di.xml

Magento\Framework\App\View\Asset\MaterializationStrategy\Symlink
Replace it with (New line)
Magento\Framework\App\View\Asset\MaterializationStrategy\copy
php bin/magento setup:static-content:deploy

-----------------------------------------------------------------
Addtocart not working:

database table: core_config_data
change in url localhost to 127.0.0.1 on given field:
web/unsecure/base_url
web/unsecure/base_url
then run command : php bin/magento setup:upgrade
------------------------------------------------------------------
Create Module:
1. Disable Magento cache
disable cache is to go to Admin ? System ? Cache Management ? select all cache 

2. Put Magento into a developer mode
php bin/magento deploy:mode:set developer

3. php bin/magento setup:upgrade

custom module:
http://www.mage-world.com/blog/create-a-module-with-custom-database-table-in-magento-2.html
http://www.mage-world.com/blog/how-to-use-model-and-collection-in-magento-2.html
