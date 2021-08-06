## Run artisan command via route 
<pre>
Route::get('/queue', function() {
         $output = [];
    \Artisan::call('queue:work --stop-when-empty', $output);
    
});

</pre>

## Add url to cornjob (cpanel)
<pre> /usr/bin/curl --silent http://domain.com/queue >/dev/null 2>&1 </pre>

## if Queue not stopping 
<pre> queue:work --stop-when-empty </pre>
<small> -stop-when-empty option ends the queue after processing all jobs</small>
