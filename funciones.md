# Cómo crear funciones personalizadas
``` 
function imprimir_fecha() {
    // Aquí incluímos el contenido
    // Ejemplo: imprimimos la fecha
    echo 'Hoy es ' . date('d/m/Y');
}

Separar las palabras con guión bajo (mi_nueva_funcion) o con mayúsculas (miNuevaFuncion)
No empezar con un número. Este nombre no serviría: 35_mi_nueva_funcion 
En WordPress se suele añadir un prefijo (normalmente el nombre del Tema), para 
 asegurarnos de que los nombres son únicos. Por ejemplo: twentythirteen_nueva_funcion

<?php imprimir_fecha(); ?>
``` 


# Funciones para el header.php
``` 
<?php bloginfo(’name’); ?> Título del blog
<?php bloginfo(’description’); ?> Descripción del blog
<?php bloginfo(’version’); ?> Versión de WordPress
<?php bloginfo(’url’); ?> URL del blog
<?php bloginfo(’pingback_url’); ?> URL de los Pingbacks del blog
<?php bloginfo(’atom_url’); ?> URL para los feeds Atom del blog
<?php bloginfo(’rss2_url’); ?> URL para los feeds RSS2 del blog
<?php bloginfo(’html_type’); ?> Versión HTML del blog
<?php bloginfo(’charset’); ?> Juego de Caracteres del blog
<?php bloginfo(’stylesheet_url’); ?> Ruta de la hoja de estilos(”‘style.css”)
<?php bloginfo(’template_url’); ?> Ruta del Theme actual
``` 

# Funciones para el resto de ficheros
``` 
<?php the_content(); ?> Contenido de los posts
<?php if(have_posts()) : ?> Si hay posts…
<?php endif; ?> Cierra la condición
<?php while(have_posts()) : the_post(); ?> Mientras haya posts, muestralos
<?php endwhile; ?> Cierra el mientras
<?php get_header(); ?> Muestra el contenido de header.php
<?php get_sidebar(); ?> Muestra el contenido de sidebar.php
<?php get_footer(); ?> Muestra el contenido de footer.php
<?php the_date() ?> Muestra la fecha
<?php the_time() ?> Muestra la hora
<?php the_time(’d-m-y’) ?> Muestra la fecha en formato d-m-y
<?php comments_popup_link(); ?> Enlace a los comentarios del post
<?php wp_title(); ?> Título del post o página
<?php the_permalink() ?> URL de post
<?php the_category(’, ‘) ?> Categorías del post
<?php the_author(); ?> Autor del post
<?php the_ID(); ?> ID del post
<?php edit_post_link(); ?> Enlace para editar el post
<?php get_links_list(); ?> Enlaces del blogroll
<?php comments_template(); ?> Muestra el contenido de Comments.php
<?php wp_list_pages(); ?> Lista las páginas del blog
<?php wp_list_cats(); ?> Lista las categorías del blog
<?php next_post_link(’ %link ‘) ?> Enlace al siguiente post
<?php previous_post_link(’%link’) ?> Enlace al post anterior
<?php get_calendar(); ?> Muestra el calendario
<?php wp_get_archives() ?> Muestra los archivos del blog
<?php posts_nav_link(); ?> Enlaces al Siguiente o Anterior Post
<?php include(TEMPLATEPATH . ‘/archivo.php’); ?> Para incluir cualquier archivo  del theme
<?php the_search_query(); ?> Valor del formulario de búsqueda
<?php _e(’Texto’); ?> Muestra “Texto”
<?php wp_register(); ?> Enlace al registro
<?php wp_loginout(); ?> Enlace al login o logout
<?php wp_meta(); ?> Meta para administradores
<?php timer_stop(1); ?> Tiempo de carga del blog
<?php echo get_num_queries(); ?> Número de consultas 
``` 
