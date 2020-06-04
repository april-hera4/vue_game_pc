<template>
  <div id="app">
    <First/>
  </div>
</template>

<script>

import First from '@/page/home'

export default {
  name: 'App',
  components: {
    First
  }
}
</script>

<style>


#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
body{
  margin:0;
  padding:0;
  background-size: 100% 100%;
    background: url('assets/img/bg_1.png') ;
  height: 100%;
    min-width: 1900px;
}
ul,li{
  list-style:none;
  margin: 0;
  padding: 0;
}
a{
  text-decoration:none;
}
a:hover{
  text-decoration:none;
}
img{
  border:0;
}
img:focus{
  border:0;
}

input::-webkit-input-placeholder {  	
    color: #0B2D46;
    font-size: 14px;
}
input:-moz-placeholder {            
    color: #0B2D46;
    font-size: 14px;
}

input::-moz-placeholder {           	
    color: #0B2D46;
    font-size: 14px;

}
input:-ms-input-placeholder {       	
    color: #0B2D46;
    font-size: 14px;
}
.header{
        min-height: 80px;
    background-color: #0B2D46;
    overflow:hidden;
    
  
    
}
.container{

        margin: 0 80px;
    overflow: hidden;
    
  
}
.header_con{
   height:80px;
    overflow:hidden;
    display: flex;
    align-items: center;
    position: relative;
    justify-content:space-between;
   
  
}
.logo{
  max-width: 160px;
    vertical-align: middle;
    line-height: 80px;
    overflow: hidden;
    float: left;

  
}
.logo img{
  vertical-align:middle;
}
.list_login{
  float: left;
  text-align: center;
  width: 627px;

  
  

}

.toggle_con {
    float: right;
}
.toggle_con ul {
    float: left;
    margin-right: 146px;
    font-size: 0;
}
.toggle_con ul li {
    display: inline-block;
    height: 80px;
    width: 214px;
    text-align: center;
}
.toggle_con ul li+li{
    margin-left: -54px;
}
.toggle_con ul li:hover{
   background: url('assets/img/hover_bg.png') ;
}

.selected {
 background: url('assets/img/hover_bg.png') ;

}


.toggle_con ul li a {
    font-style: italic;
    color: #fff;
    display: block;
    margin-top: 23px;
    cursor: pointer;
}
.toggle_con ul li span {
    font-style: italic;
    font-size: 18px;
    color: #fff;
    display: block;
}
.toggle_con ul li i {
    font-style: italic;
    font-size: 12px;
    color: #fff;
    margin-top:2px;
    display:block;
}
.toggle_con .login{
    float:right;
    font-size: 0;
    padding-top:23px;
}

.login input{
    width: 150px;
    height: 34px;
    border-radius: 4px;
    padding: 0 8px;
    background-color: #3c576b;
    box-sizing: border-box;
    color:#fff;
    border:none;
    
}
.login input+input{
    margin-left: 20px;
    margin-right: 20px;
}
.login button{
    padding: 0 20px;
    height: 34px;
    background-color: #0ba7d4;
    color: #fff;
    font-size: 14px;
    border-radius: 10px;
    cursor:pointer;
    border:none;

}
.login button:active{
  background:000;
   opacity:0.5;
   border:none;
}

.list_login ul {
  margin:0;
   overflow:hidden;
  box-sizing:border-box;
}
.list_login ul li{
     display: inline-block;
    height: 80px;
    width: 214px;
    text-align: center;
    border: 1px saddlebrown solid;
  
}
.list_login ul li:hover{
  background:  url('assets/img/hover_bg.png');
}
.list_login ul li span{
  display:block;
  font-style: italic;
  font-size: 18px;
  color: #fff;
  display: block;
}
.list_login ul li i{
  font-style: italic;
  font-size: 12px;
  color: #fff;
}
.login-btn{
width: 420px;
  float:right;


}
.login-btn input{
    width: 150px;
    height: 34px;
    border-radius: 4px;
    padding: 0 8px;
    background-color: #3c576b;
    box-sizing: border-box;
    
}
.login-btn input+input{
    margin-left: 20px;
    margin-right: 20px;
}
.login-btn .lg_btn{
    padding: 0 20px;
    height: 34px;
    background-color: #0ba7d4;
    color: #fff;
    font-size: 14px;
    border-radius: 10px;
    display:inline-block;
    text-align:center;
    line-height:34px;
    box-sizing:border-box;
    
}
</style>
