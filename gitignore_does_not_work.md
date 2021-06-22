## NOTE : Before proceeding with this solution, commit all changes you do not want to lose!
<pre>
git rm -r --cached .;
git add .;
git commit -m "Untracked files issue resolved to fix .gitignore";
</pre>
## To stop tracking a single file file but not delete it from your filesystem use the following:
<pre>
git rm --cached <file>;
</pre>
## Another issue: file removed from .gitignore filters does not appear to be tracked
<pre>
git add -f <file>;
git commit -m "Re-Adding ignored file by force";
</pre>
