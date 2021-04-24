## add custome theme in the wordpress cms 
<ol>
<li> copy your custom theme folder and place into <b> wp_content/themes </b> </li>
    <li> make <b>style.css</b>  file in the theme root directory and place following code <br>
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
    <li>and go to admin panel and activate the theme</li>
</ol>

## Make basic files in the your theme root directory
   <ol>
       <li> <b>header.php </b> - put the header part of the your site. Also put the <b> wp_head()</b> with php tag </li>
        <li> <b>footer.php</b>  - put the footer part of the your site. Also put the <b> wp_footer()</b> with php tag  </li>
        <li> <b>functions.php</b> - you need to make and registers , initilized the stylesheet and scripts etc or make weigets</li>
  </ol>
  
## Linking the stylesheets with functions.php
<ol>
   <li> If you have a cdn links place theme as usual</li>
  <li>Make function (<b>load_stylesheet()</b>) and load stylesheet <br>
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
  <li> If you have a cdn links place theme as usual</li>
  <li>Make function (<b>load_scripts()</b>) and load scripts <br>
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


