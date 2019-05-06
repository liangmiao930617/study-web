# study-web
移动端适配

我总结一下我写移动端页面时做的适配：

首先百分比、flex，其次是mediaquery:

@media screen and (...){
}
<link rel="stylesheet" type="text/css" href="" media="...">


js:  rem是根据html的font-size决定，根据不同屏幕来设置它的font-size的值
     let htmlWidth = document.documentElement.clientWidth || document.body.clientWidth
     let htmlDom = document.getElementsByTagName('html')[0]
     htmlDom.style.fontSize = htmlWidth / 10 + 'px'
     
scss:

      @function px2rem($px){
       $rem: 37.5px;
       @return ($px / $rem) + rem;
     }

     .hello{
       width:px2rem(100px);
       height:px2rem(100);
       &.b{
         width:px2rem(50px);
         height:px2rem(50px);
       }
     }

