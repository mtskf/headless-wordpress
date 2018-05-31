# functions.php
It is recommended to point Access-Control-Allow-Origin to a specific domain.

- functions.php (default: wild card `*` is set)
```
<?php
function my_customize_rest_cors() {
  remove_filter( 'rest_pre_serve_request', 'rest_send_cors_headers' );
  add_filter( 'rest_pre_serve_request', function( $value ) {
    header( 'Access-Control-Allow-Origin: *' );
    return $value;
  });
}
add_action( 'rest_api_init', 'my_customize_rest_cors', 15 );
?>
```
- Example:
```
header( 'Access-Control-Allow-Origin: https://example.com' );
```


# Recommended plug-ins
- [Advanced Custom Fields](https://wordpress.org/plugins/advanced-custom-fields/)
- [ACF to REST API](https://wordpress.org/plugins/acf-to-rest-api/)
