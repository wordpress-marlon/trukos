# Log en wordpress
## wp-config.php

``` 
define( 'WP_DEBUG', true);

// Enable Debug to the / wp-content/debug.log file
define( 'WP_DEBUG_LOG', true);
``` 


## functions.php
``` 
if (!function_exists('write_log')) {

    function write_log($log) {
        if (true === WP_DEBUG) {
            if (is_array($log) || is_object($log)) {
                error_log(print_r($log, true));
            } else {
                error_log($log);
            }
        }
    }

}

write_log('THIS IS THE START OF MY CUSTOM DEBUG');
``` 

## Log Wordpress
``` 
$variable = $_COOKIE;

echo '<pre>';
print_r($variable);
echo '</pre>';
die();
``` 
