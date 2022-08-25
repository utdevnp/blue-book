 ### Here our this.file is object 
 <code>  this.files </code>
 
 ### You can change object into array 
 <code>this.files = Object.values(this.files); </code>
 
 ### If you need to splice array 
 <code> this.files.splice(index, 1); </code>
 <b> splice takes array index and remove that array index for More <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice">Array.prototype.splice()</a> </b>
 ### Full code 

 ```
   clearFile(name, index) {
   // this.files is a object 
   this.files = Object.values(this.files); // Object.values convets object into array 
   this.files.splice(index, 1);
   
 ```
