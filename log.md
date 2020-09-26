# Log en wordpress
## wp-config.php

``` 
define( 'WP_DEBUG', true);

// Enable Debug to the / wp-content/debug.log file
define( 'WP_DEBUG_LOG', true);
``` 



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
