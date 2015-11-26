初学margin的几个坑和css reset
===============================
1.上下margin会叠压。
        这个大家都知道。

2.两个盒子是父子级关系时，子元素的margin-top会传递给父级。
        换句话说，给了子元素一个margin-top完全没效果，这个样式反而污染了父元素（坑啊！）

解决办法：给父级元素设置padding（变相完成子元素的margin效果）
PS：给父元素加padding后，不要忘了相应的减少weight和height，否则父元素会被撑大。

3.关于css reset
        浏览器默认的任何东西，都不要使用。
        *{}尽量不要用，因为*会选中所有元素，性能很差。
        
PS:个人常用css reset

        body,p,dl,dd,h1,h2,h3,h4,h5,h6{margin:0;}
        a{text-decoration:none;}
        img{border:none; vertical-align:top;}
        ol,ul{margin:0;padding:0;list-style:none;}