<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}
html,body {
  width: 100%;
  height: 100%;
}
#app {
  width: 100%;
  height: 100%;
}
.layout {
  width: 1200px;
  height: 100%;
  margin: 0 auto;
}
li {
  list-style-type: none;
}
a {
  text-decoration: none;
  color: black;
  cursor: pointer;
}
input {
  border: none;
  outline: none;
}
.fl {
  float: left;
}
.fr {
  float: right;
}
.swiper-container {
    width: 100%;
    height: 550px;
    position: absolute;
    top: 0;
    left: 0;
    z-index: 0;
}
.tips {
    width: 100%;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
}
.tips .thumbs {
    display: inline-block;
    width: 100%;
    height: 100%;
    text-align: center;
    font-style: normal;
}
.tips .thumbs>span {
    font-size: 12px;
    display: inline-block;
    padding: 2px 9px 0;
    margin: 0 auto;
    height: 22px;
    border-radius:  0 0 8px 8px;
    color: white;
}
.tips .thumbs>span.color1 {
    background-color: #FF6A6E;
}

.tips .thumbs>span.color2 {
    background-color: #68BEFF;
}
.desc{
    color: #777777;
    line-height: 18px;
    padding: 0 10px;
    margin: 2px 20px 7px;
}
.desc1{
    padding-bottom: 0;
    width: 100%;
    height: 36px;
    background-color: #f3f3f3;
    text-align: center;
    font-size: 14px;
    line-height: 36px;
    color: #777777;
    border-radius: 0 0 10px 10px;
}
.price{
    color: #ca151d;
    font-size: 14px;
}
.layout ul>li .img1>img{
  widows: 100%;
  height: 100%;
}
.layout ul>li .img2>.p-img {
    width: 150px;
    height: 150px;
    margin: 35px auto 0;
}
.layout ul>li .img2>.p-img>img {
    width: 150px;
    height: 150px;
}
.layout ul>li .img2>p.title {
    font-size: 14px;
    margin: 12px 10px 0;
}
.layout ul>li .img2>p.title:hover {
    color: #ca151d;
}
.goods2-header{
    height: 36px;
    width: 100%;
    padding-bottom: 10px;
}
.goods2-header .left{
    float: left;
    display: flex;
}
.goods2-header .left ul{
    float: left;
}
.goods2-header .left ul>li{
    float: left;
}
.goods2-header .left ul>li>a{
    margin-left: 24px;
    color: #999999;
    font-size: 14px;
    line-height: 32px;
}
.goods2-header .left ul>li>a:hover{
    color: #ca151d;
}
.goods2-header .right{
    float: right;
}
.goods2-header .right li>a{
    font-size: 14px;
    line-height: 32px;
    color: #333333;
    padding-right: 30px;
    position: relative;
}
.goods2-header .right li>a:hover{
    color: #ca151d;
}
.goods2-header .right li>a>img{
    width: 12px;
    height: 12px;
    position: absolute;
    top: 2px;
    right: 14px;
}
</style>
