# functions.php
``` 
<?php
/**
 * Astra functions and definitions
 *
 * @link https://developer.wordpress.org/themes/basics/theme-functions/
 *
 * @package Astra
 * @since 1.0.0
 */

function register_cpt_producto() {
    $labels = array( 
        'name' => _x( 'Productos', 'producto' ),
        'singular_name' => _x( 'Producto', 'producto' ),
        'add_new' => _x( 'Añadir nuevo', 'producto' ),
        'add_new_item' => _x( 'Añadir Producto', 'producto' ),
        'edit_item' => _x( 'Editar Producto', 'producto' ),
        'new_item' => _x( 'Nuevo Producto', 'producto' ),
        'view_item' => _x( 'Ver Producto', 'producto' ),
        'search_items' => _x( 'Buscar Productos', 'producto' ),
        'not_found' => _x( 'No se encontraron productos', 'producto' ),
        'not_found_in_trash' => _x( 'No se encontraron producto en la basura', 'producto' ),
        'parent_item_colon' => _x( 'Producto Padre:', 'producto' ),
        'menu_name' => _x( 'Productos', 'producto' ),
    );  // Creamos un array para $args  
$args = array( 
        'labels' => $labels,
        'hierarchical' => false,
        'supports' => array( 'title', 'editor', 'thumbnail' ),
        'public' => true,
        'show_ui' => true,
        'show_in_menu' => true,
        'show_in_nav_menus' => true,
        'publicly_queryable' => true,
        'exclude_from_search' => false,
        'has_archive' => true,
        'query_var' => true,
        'can_export' => true,
        'rewrite' => true,
        'capability_type' => 'post',
    );

    register_post_type( 'producto', $args );
}

add_action( 'init', 'register_cpt_producto' );
``` 
