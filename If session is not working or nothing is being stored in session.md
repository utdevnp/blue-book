## If session is not working or nothing is being stored in session, check if your session is writable

<pre>
    if (!is_writable(session_save_path())) {
      echo 'Session path "'.session_save_path().'" is not writable for PHP!'; 
    }
</pre>
