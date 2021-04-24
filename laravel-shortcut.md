## Artisan commands with controller / routes
<ol>
  <li> Example :  Run migration <br>
<pre>
// in route 
Route::get('/migration', function() {
 $output = [];
 Artisan::call('migrate', $output); 
});
</pre>
<b> OR </b>
<br>
<pre>
// in controller 
function index(){
 $output = [];
 Artisan::call('migrate', $output);
}
</pre>
  </li>
</ol>
