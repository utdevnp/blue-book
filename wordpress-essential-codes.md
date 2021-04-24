# Welcome :blue_book:
### You must have a basic knowlwdge of wordpress installation configure and how it works.
## add custome theme in the wordpress cms 
<ol>
<li> Copy your custom theme folder and place into <b> wp_content/themes </b>. </li>
    <li> Make <b>style.css</b>  file in the theme root directory and place following code <br>
<pre>
    /*
    Theme Name: Theme Name
    Theme URI: 
    Author: Your name
    Email: your@gmail.com
    Author URI: 
    */
</pre>
</li>
    <li>And go to admin panel and activate the theme.</li>
</ol>

## Make basic files in the your theme root directory
   <ol>
        <li> <b> index.php </b> (main template file) </li>
        <li> <b>header.php </b> - Put the header part of the index.php. Also put the <b> wp_head()</b> with php tag. </li>
        <li> <b>footer.php</b>  - Put the footer part of the index.php. Also put the <b> wp_footer()</b> with php tag.  </li>
        <li> <b>functions.php</b> - You need to make and register, initilize the stylesheet and scripts, etc or make widgets.</li>
  </ol>
  
## Linking the stylesheets with functions.php
<ol>
   <li> If you have a cdn links place theme as usual.</li>
  <li>Make function (<b>load_stylesheet()</b>) and load stylesheet. <br>
<pre>
function load_stylesheet(){

  wp_register_style("styleone",get_template_directory_uri()."/assets/style-one.css",array(),"1","all");
  wp_enqueue_style("styleone");

}
add_action("wp_enqueue_scripts","load_stylesheet"); 
// it helps load your style and script assets according to wordpress asset management.
</pre>
  </li>
</ol>

## Linking the scripts with functions.php

<ol>
  <li> If you have a cdn links place theme as usual.</li>
  <li>Make function (<b>load_scripts()</b>) and load scripts. <br>
<pre>
function load_scripts(){
  wp_register_script("jquery",get_template_directory_uri()."/assets/js/jquery-3.2.1.min.js",array(),"1","all");
  wp_enqueue_script("jquery");
}
</pre>
  </li>
</ol>


  
## Linking assets in the file like images , favicon, background image etc 
<ol>
    <li> Link your asset to show image of the theme , use <br>
<pre>
bloginfo("template_directory")/assets/images/banner1.jpg
</pre>
</li>
</ol>

<b>Example</b>:  

 ```html
  <img src=" bloginfo("template_directory") /assets/images/banner1.jpg" alt=""/> 
 ```

## Including header and footer .php in to the template page like index.php
<ol>
    <li> use <b> get_header() </b> and <b> get_footer() </b>  in the template top and bottom.</li>
</ol>

## Registering the nav/menu in the function.php
<ol>
    <li> Use following code to register menu. </br>
        <pre>
add_theme_support( 'menus' );
register_nav_menus(
    array(
        'top_menu' => 'Header menu',
        'footer_menu' => 'Footer menu',
    ) 
);
        </pre>
         <b> Your register menu shows in to wp-admin > theme > menu area.  </b>
    </li>
</ol>

## Showing the register menu in  theme 
<ol>
    <li>Place the following code in the menu section of your theme, may be header.php <br>
    <pre>
wp_nav_menu(
    array(
        'theme_location'=>"top_menu", // must be same in function.php register_nav_menus
        'menu'=>"menu-desktop-menu", // id of the element
        'container'=>'ul', // menu ul 
        "menu_class"=>"menu" // menu ul class
    )
);
    </pre>
    </li>
</ol>

## Register and making the weigets function.php 
<ol>
    <li> Use following code to register widgets. </br>
        <pre>
function sociallinks_widgets_init() {
 register_sidebar(
  array(
   'name'          => __( 'Social Links', 'theme_name' ),
   'id'            => 'sidebar-1',
   'description'   => __( 'Add widgets here to appear in your footer.', 'theme_name' ),
   // you may find more options 
  )
 );
}
        </pre>
        <b> Your register widgets shows in to wp-admin > theme > widgets area.  </b>
    </li>
</ol>

### Happy Coding :smile:
