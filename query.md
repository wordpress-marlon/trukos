
# Mostrar últimos 4 post
``` 
<ul>         
        <?php query_posts('showposts=4'); ?>
        <?php if (have_posts()) :while ( have_posts() ) : the_post(); ?>
        <li class="lista-page">
         <div class="lista-page-img"><?php if (has_post_thumbnail()) {the_post_thumbnail('list_blog_index'); } ?></div>
         <article>
           <hgroup><p><a href="<?php the_permalink();?>">» <?php  the_title(); ?></a></p></hgroup>
           <p><?php  the_excerpt(); ?></p>
         </article>
       </li>
     <?php endwhile; else: ?>
     <h1> No se encontraron ... </h1>
   <?php endif; ?>  
 </ul>
``` 
