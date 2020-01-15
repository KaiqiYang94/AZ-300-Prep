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


Pluralsight
``` js
var jq = document.createElement('script');
jq.src = "https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js";
document.getElementsByTagName('head')[0].appendChild(jq);
// ... give time for script to load, then type (or see below for non wait option)
jQuery.noConflict();


var str = ""
$('a[class*=itle]').each(function( index ) {
  if(this.innerHTML){
    str = str + "### [";
    str = str + this.innerHTML + "](" + this.href + ")\n";
  }
});
console.log(str)

```


