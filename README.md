# Installation (Composer)

    {
        "require": {
            "isometriks/linode-php": "dev-master"
        }
    }
    
## Usage

```php
<?php

try {
    $linode = new Linode\Api('apikey');
    $a = $linode->linode_list();
    $b = $linode->domain_list(array('DomainID' => 23233));
    
    var_dump($a);
    var_dump($b);
} catch (Linode\Exception $e) {
    echo $e->getMessage();
}
```

#### To perform a batch request

```php
<?php
    
try {
    $linode = new Linode\Api('apikey');
    $linode->batching = true;
    $linode->linode_list();
    $linode->domain_list();
    $result = $linode->batchFlush();
        
    var_dump($result);
} catch (Linode\Exception $e) {
    echo $e->getMessage();
}
```

For more information about api methods visit <http://www.linode.com/api>
