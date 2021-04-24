## Route with optional parameter
<ol>
  <li> <pre> 
  Route::get("user/{user_type?}");
  Route:post("user/{user_type?}");
  </pre> </li>
</ol>

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
