# Remove-the-word-Product-from-the-navigation-bar
Remove the word “Product” from the navigation bar
/*
 * Hide "Products" in WooCommerce breadcrumb
 */
function woo_custom_filter_breadcrumbs_trail ( $trail ) {
  foreach ( $trail as $k => $v ) {
    if ( strtolower( strip_tags( $v ) ) == 'products' ) {
      unset( $trail[$k] );
      break;
    }
  }
 
  return $trail;
}
 
add_filter( 'woo_breadcrumbs_trail', 'woo_custom_filter_breadcrumbs_trail', 10 );
