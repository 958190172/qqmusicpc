<template>
  <div class="home" @mouseenter="i_show=!i_show" @mouseleave="i_show=!i_show">
	  <h1 id="song_menu">歌单推荐</h1>
	  <ul id="home_header">
		  <li><a>为你推荐</a></li>
		  <li><a>情歌</a></li>
		  <li><a>网络歌曲</a></li>
		  <li><a>九月推荐</a></li>
		  <li><a>官方歌单</a></li>
		  <li><a>经典</a></li>
	  </ul>
	  <div class="re_songs">
           
		   <template v-for="song in resongs">
		   <div :key="song.order" class="songs">
			   <router-link to="/about">
			   <img :src="song.url" 
			  
			   @mouseenter="big" 
			   @mouseleave="small">
			   </router-link>
			   <p>{{song.tip}}</p>
			   <p>播放量：{{song.num}}万</p>
			   
		   </div>
		   </template>
           <i class="el-icon-arrow-left" id="i_left" :class="{movein:i_show}" @click="red"></i>
           <i class="el-icon-arrow-right" id="i_right" :class="{movein_right:i_show}" @click="plu"></i>
	 </div>
  </div>
</template>

<script>


export default {
  name: 'Home',
  methods: {
  	plu() {
  		if(this.re_sons_n<2) {
			this.re_sons_n++;
		} else {
			if(this.re_sons_n === 2) {
				this.re_sons_n=0;
			}
		}
			
  	}, 
	red(){
		if(this.re_sons_n>0) {
			this.re_sons_n--;
		} else {
			if(this.re_sons_n===0){
				this.re_sons_n=2;
			}
		}
		
		
	},
	big(event){
		event.target.classList.add('grow');
	},
	small(event){
		event.target.classList.remove('grow');
	}
  },
  watch: {
  	re_sons_n(newValue) {
  		var div_first = document.getElementsByClassName('songs')[0];
		div_first.style.marginLeft = -newValue*this.re_len + 90 + 'px';
  	}
  },
  
  data(){
	  return {
		  i_show:false,
		  re_sons_n:0,
		  re_len: 1340,
		  
		  resongs: [
			  {
				  url: require("../assets/images/re_1.png"),         
				  tip: '爆款收割机！时下流行热歌集合',
				  num: '1037.5',
				  order: 1
			  },
			  {
			  				  url: require('../assets/images/re_2.png'),
			  				  tip: '致失恋|想起你时还总是会流泪',
			  				  num: '901.2',
			  				  order: 2
			  },
			  {
			  				  url: require('../assets/images/re_3.jpg'),
			  				  tip: '8090回忆杀|卡带里的暗恋情歌',
			  				  num: '9.3',
			  				  order: 3
			  },
			  {
			  				  url: require('../assets/images/re_4.jpg'),
			  				  tip: '清空悲悯|破碎心愿无法弥补',
			  				  num: '114.6',
			  				  order: 4
			  },
			  {
			  				  url: require('../assets/images/re_5.png'),
			  				  tip: '你来友情客串，我却藽情演出',
			  				  num: '356.4',
			  				  order: 5
			  },
			  {
			  				  url: require('../assets/images/re_6.jpg'),
			  				  tip: '翻唱片段|长路漫漫，伴你身旁',
			  				  num: '306.6',
			  				  order: 6
			  },
			  {
			  				  url: require('../assets/images/re_7.jpg'),
			  				  tip: '暴露年龄！学生时代MP3里听的歌',
			  				  num: '1132.6',
			  				  order: 7
			  },
			  {
			  				  url: require('../assets/images/re_8.png'),
			  				  tip: '欧美|这些999+弹幕神曲你听过吗',
			  				  num: '59.9',
			  				  order: 8
			  },
			  {
			  				  url: require('../assets/images/re_9.jpg'),
			  				  tip: '101位歌手代表取，不得不爱',
			  				  num: '6390.5',
			  				  order: 9
			  },
			  {
			  				  url: require('../assets/images/re_10.png'),
			  				  tip: '耳机分你一个，想和你分享好心情',
			  				  num: '1930.7',
			  				  order: 10
			  },
			  {
			  				  url: require('../assets/images/re_11.jpg'),
			  				  tip: '洗脑专用-奇葩洗脑神曲',
			  				  num: '584.8',
			  				  order: 11
			  },
			  {
			  				  url: require('../assets/images/re_12.png'),
			  				  tip: '袅袅请引起缓缓舒胸怀',
			  				  num: '37.6',
			  				  order: 12
			  }
		  ]
	  }
  }
  
};
</script>


<style scoped>
	
	/*css for nav*/
	.home {
		font-size: 14px;
		padding: 0;
		padding-top: 1.5rem;
		background-color: #F3F3F3;
	}
	#home_header li {
		display: inline;
		margin: 0 1.5rem;
	}
	#home_header {
		margin-top: 1.5rem;
	}
	a:hover {
		color: forestgreen;
	}
	
	
	/*css for main*/
	.re_songs {
		position: relative;
		display: flex;
		flex-wrap: nowrap;
		width: 100%;
		height: 300px;
		overflow: hidden;
		

		margin-top: 1.5rem;
	
		
	}
	.re_songs div {
		flex: 0 0 auto;
	
		margin: 0 10px;
	}
	.re_songs div:first-child {
		margin-left: 90px;
	}
	.re_songs div:nth-child(6) {
		margin-left: 150px;
	}
	.re_songs div:nth-child(11) {
		margin-left: 150px;
	}
	
	.re_songs img {
		width: 220px;
		height: 11rem;
		margin: 0;
		transition: transform 0.5s linear;
	}
	
	#i_left {
		position: absolute;
		top: 4rem;
		left: -100px;
		font-size: 60px;
		background-color: #EBEAEA;
		transition: transform 0.6s linear;
		
	}
	#i_right {
		position: absolute;
		top: 4rem;
		font-size: 60px;
		right: -100px;
		background-color:#EBEAEA;
		transition: transform 0.6s linear;
	}
	.movein {
		transform: translate(100px);
	}
	.movein_right {
		transform: translate(-100px);
	}
	.grow {
		transform: scale(1.1);
	}
	
</style>
