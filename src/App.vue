<template>
  <div id="app">
    <div id="nav">
		<div id="header">
			<div id="qqtitle">
				<img src="./assets/images/logo.png" />
			</div>
			<ul id="top_nav">
				<router-link to="/"><li id="music_house"><a>音乐馆</a></li></router-link>
				<li><a>我的音乐</a></li>
				<li id="kh"><a>客户端</a><img src="./assets/images/mark_1.png" id="mark_1"></li>
				<li><a>开放平台</a></li>
				<li><a>VIP</a></li>
			</ul>
			<div id="search_login">
				<p>
				<input placeholder="搜索音乐、MV、歌单、用户">
					
					<i class="el-icon-search" id="s1"></i>
					
				<span id="log">登录</span>
				<el-button id="vip">开通VIP<i class="el-icon-caret-bottom el-icon--right"></i> </el-button>
				<el-button>充值<i class="el-icon-caret-bottom el-icon--right"></i></el-button>
				</p>
				
				
				
			</div>
			<ul id="sub_nav">
				<li><a>首页</a></li>
				<li><a>歌手</a></li>
				<li><a>新碟</a></li>
				<li><a>排行榜</a></li>
				<li><a>分类歌单</a></li>
				<li><a>电台</a></li>
				<li><a>MV</a></li>
				<li><a>数字专辑</a></li>
				<li><a>票务</a></li>
			</ul>
		</div>
      
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
 font-size: 18px;
}

/*reset.css*/
html,body,div,span,applet,object,,h1,h2,h3,h4,h5,h6,p,blockquote,pre,a,abbr,acronym,address,big,cite,code,del,dfn,em,img,ins,kbd,q,s,samp,small,strike,strong,sub,sup,tt,var,b,u,i,center,dl,dt,dd,ol,ul,li,fieldset,form,label,legend,table,caption,tbody,tfoot,thead,tr,th,td,article,aside,canvas,details,embed,figure,figcaption,footer,header,hgroup,menu,nav,output,ruby,section,summary,time,mark,audio,video {
	margin:0;
	padding:0;
	border:0;
	font-size:100%;
	font:inherit;
	font-weight:normal;
	vertical-align:baseline;
}
/* HTML5 display-role reset for older browsers */
article,aside,details,figcaption,figure,footer,header,hgroup,menu,nav,section {
	display:block;
}
ol,ul,li {
	list-style:none;
}
blockquote,q {
	quotes:none;
}
blockquote:before,blockquote:after,q:before,q:after {
	content:'';
	content:none;
}
table {
	border-collapse:collapse;
	border-spacing:0;
}
th,td {
	vertical-align:middle;
}
/* custom */
a {
	outline:none;
	color:#000000;
	text-decoration:none;
	-webkit-backface-visibility:hidden;
}
a:focus {
	outline:none;
}
input:focus,select:focus,textarea:focus {
	outline:-webkit-focus-ring-color auto 0;
}



#header {
	display: grid;
	grid-template-columns: 20% 40% 40%;
	grid-template-rows: 90px 50px;
	line-height: 1.5rem;
}
#qqtitle {
	grid-column: 1/2;
	grid-row: 1/2;
	text-align: right;
	vertical-align: sub;
}

#qqtitle img {
	width: 168px;
	height: 50px;
	margin: 0.5rem 0;
	padding: 0 0;
}
#top_nav {
	grid-column: 2/3;
	grid-row: 1/2;
	text-align: left;

}
#music_house {
	background-color: #31C27C;
}
#kh {
	position: relative;
}
#mark_1{
	position: absolute;
	width: 35px;
	height: 15px;
	top: 0.5rem;
	left: 1.5rem;
}
#search_login {
	grid-column: 3/4;
	grid-row: 1/2;
    text-align: left;
	margin-top: -0.5rem;
}
#search_login input {
	
	width: 190px;
	height: 38px;
	padding: 0 0;
	margin-right: 1rem;
	border: 1px solid aliceblue;
	border-radius: 5px;
}
#vip {
	background-color: #31c27c;
	margin-left: 10px;
}
#sub_nav {
	grid-column: 1/4;
	grid-row: 2/3;
	font-size: 16px;
	
}
#sub_nav li {
	margin: 0 0.4rem;
}
#header ul li {
	display: inline;
	padding: 1.5rem 15px;
}
#s1 {
	margin-left: -2rem;
}
#log{
	margin-left: 1rem;
	font-size: 16px;
}
a:hover {
	color: green;
}




</style>
