# 1 - Estructura de Wordpress  (wordpress\wp-content\themes)
``` 
index.php
<?php get_header(); ?>
<?php get_sidebar(); ?>
<?php get_footer(); ?>


Style.css
/*
Theme Name: Tema 01
Theme URI: www.miweb.com
Description: Aprendiendo 
Version:1
Author : auto
Author URL: direccion web 
*/
``` 

# 2- Arreglamos las rutas de los archivos
``` 
<link href=<?php bloginfo('stylesheet_url'); ?>  rel="stylesheet" type="text/css"/>
<link rel="stylesheet" type="text/css" href="<?php bloginfo('template_url')?>/css/n.css">
<?php include(TEMPLATEPATH. '/slideshow.php')   ?>
``` 

# 3 - Creamos los menu
``` 
functions.php
// Registramos un menu
register_nav_menus( array(
'menu' => 'Menu superior',
'menu_footer' => 'Menu footer'
));

// Registramos las imagenes
add_theme_support('post-thumbnails');
add_image_size('slider_thumbs',470,300,true);
add_image_size('list_article_thumbs',450,370,true);



<nav>
                <ul>
                     <li> <a href="#"> Inicio </a> </li>
                     <li> <a href="#"> Acerca de </a></li>
                     <li><a href="#"> Contacto </a> </li>
                     <li><a href="#"> Pagina de ejemplo </a> </li>
                </ul>	
            </nav>

<nav>
                <?php  wp_nav_menu(
                   array(
                  'container' => '<ul id="menu-top">%3$s</ul>',
                  'theme_location' => 'menu'
                  )); ?>
            </nav>	

``` 
# 4- Creamos la lista de artículos
``` 
<section id="article_list">
                  <article> 
                                 <img class="thumb"  src="http://lorempixel.com/300/200/sports/1/">
                                 <hgroup><h2><a href="#">Titulo del articulo 1</a></h2></hgroup>
                                  <p class="date">16 de dicciembre de 2014 en 
                                  <a href="#">Categoria 1</a></p>
                                  <p class="extract"> Al contrario del pensamiento popular, </p>
                  </article>
 	  </section> <!--article_list -->






section id="article_list">
                    <?php query_posts("paged=$paged"); ?>
                <?php query_posts("category_name=slider"); ?>
                   	<?php if (have_posts()) :while ( have_posts() ) : the_post(); ?>
                      <article>                           
                          <div class="thumb"><a href="<?php the_permalink();?>">
                             <?php if (has_post_thumbnail()) {the_post_thumbnail('list_articles_thumbs'); } ?>
                          </a></div>
                        <hgroup><h2><a href="<?php the_permalink(); ?>"><?php the_title(); ?></a></h2></hgroup>
                        <div class="date"><?php the_date(); ?> en <span> <?php the_category(); ?> </span> </div>
                        <div class="extract"><?php the_excerpt();?></div>
                      </article>

                      <?php endwhile; else: ?>
                      <h1> No se encontraron Articulos </h1>
                      <?php endif; ?>
                  <div id="pagination"> 
                         <p> 
                                <?php previous_posts_link('<--  Post Anterior')?>
                                <?php next_posts_link('Post Siguiente -->')?> 
                         </p>
                   </div>
             </section> <!--article_list -->
``` 
# 5-Agregando los barras de admin
``` 
header.php : <?php wp_head();?>
footer.php : <?php wp_footer();?>
``` 


# 6- Agregando los widgets
``` 
<aside>
                   	    <section class="widget">
                   	    	<h3> Widget </h3>
                   	    	<ul>
                   	    		<li> <a href="#"> Lorem Ipsum</a></li>
                   	    		<li> <a href="#"> Lorem Ipsum</a></li>
                   	    		<li> <a href="#"> Lorem Ipsum</a></li>
                   	    		<li> <a href="#"> Lorem Ipsum</a></li>
                   	    		<li> <a href="#"> Lorem Ipsum</a></li>
                   	    	</ul>
                   	    </section>
                   </aside>	

// Registramos los widgets functions.php

//Registramos los widgets
register_sidebar(array(
      'name' => 'Sidebar',
     'before_widget' => '<section class="widget">',
     'after_widget' => '</section>',
     'before_title' => '</h3>',
     'after_title' => '</h3>',
));


<aside>                   	
      <?php if( !function_exists('dynamic_sidebar') ||
                                                                                 !dynamic_sidebar('Sidebar')): endif; ?>
</aside>
``` 

# 7-Agregando los comentarios en los post  (single.php)
``` 
<div id="comentarios">
                       <h3>Comentarios</h3>
                             <div id="caja_comentarios">
                                     <?php comments_template(); ?>
                           </div>
               </div>	
``` 
# 8- Agregando link pagina de inicio
``` 
<h3>  <a href=” <?php  bloginfo(“wpurl”); ?> ” > Inicio</a></h3>
``` 

