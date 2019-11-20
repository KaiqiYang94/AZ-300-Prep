``` js
// all
var str = ""
$("a.is-block").each(function( index ) {
  if(this.innerText){
    if(!$(this).hasClass("unit-title")){
      str = str + "# [";
    }else{
      str = str + "- [";
    }
    str = str + this.innerText + "](" + this.href + ")\n";
  }
});
console.log(str)

//time
$(".module-time-remaining").each(function(){console.log(this.innerText)})


//end
var str = ""
$("div.section a").each(function( index ) {
  if(this.innerText){
    str = str + "- [";
    str = str + this.innerText + "](" + this.href + ")\n";
  }
});
console.log(str)
```