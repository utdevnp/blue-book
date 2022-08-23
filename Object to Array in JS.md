 clearFile(name, index) {
  // this.files is a object 
  this.files = Object.values(this.files); // Object.values convets object into array 
  this.files.splice(index, 1);
},
