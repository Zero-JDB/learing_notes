干货推荐，每个程序员都会的35个jQuery小技巧！
============================================
1. 禁止右键点击
>$(document).ready(function(){

>    $(document).bind("contextmenu",function(e){

>        return false;

>    });

>});