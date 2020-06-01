<template>
<div>
  <div class="header">
    <div class="container">
      <div class="header_con">
        <div class="logo">
          <a><img src="@/assets/img/logo.png" /></a>
        </div>
        <div class="toggle_con">
                <ul>
                <li   v-for="(list,i) in lists" >
                <a><span>{{list.title}}</span>
              <i>{{list.en}}</i></a>
              
            </li>
                   
                </ul>
                <div class="login">

                    <form action="">
                        <input type="text" placeholder="请输入账号">
                        <input type="text" placeholder="请输入密码">
                        <button>登录</button>
                    </form>
                </div>
            </div>

      </div>
    </div>
  </div>
    <div style="position: relative;margin:0 auto;overflow:hidden;">
    <!-- swiper1 -->
    <div v-swiper:swiperTop="swiperOptionTop" class="gallery-top">
      <div class="swiper-wrapper" style="ovflow:hidden">
        <div class="swiper-slide" v-for="item in imgTop" :key="item.name">
        <el-link :underline="false"   class="go">玩游戏<img src="@/assets/img/icon_go.png"></el-link>
            <img :src="item.imgUrl" class="swiper_img"/>
            <div class="slide_bg">
             
              <div class="slide_txt">
              <div class="slide_top">
                <div class="slide_title"><span>{{item.name}}<em>{{item.enlish}}</em></span><i><em>{{item.des}}</em><em>{{item.desc}}</em></i></div>
                <div class="slide_dep" id="slide_dep">
                  <em>{{item.dev}}</em>
                  <span>
                    <strong> <i><img src="@/assets/img/icon_single.png" /></i><em>单机游戏</em></strong> 
                    <strong> <i><img src="@/assets/img/icon_volume.png" /></i><em>大小：24M</em></strong>
                  </span>
                </div>
               </div>
               <div class="slide_bor"></div>
              <div class="slide_bot">
                <em>游戏简介：</em>
                <span>《开心消消乐》是一款乐元素研发的一款三消类休闲游戏。2013年8月，正式在网页版上线，在2014年8月推出了安卓版本和IOS版本。游戏以救村长为目的，玩家开始了一段开心的闯关旅程。在2015年《开心消消乐》荣获玩家最喜爱的移动单机游戏奖</span>
              </div>
              </div>
              </div>
            </div>
        </div>
        <div id="pag_slide" class="swiper-pagination swiper-pagination-bullets " ></div>
      </div>
    </div>
    <!-- swiper2 Thumbs -->
    <div class="small_horz" >
    <div v-swiper:swiperThumbs="swiperOptionThumbs" class="gallery-thumbs">
    <div class="swiper-wrapper" >
        <div class="swiper-slide" v-for="item in imgThumbs" :key="item.name">
            <img :src="item.imgUrl" class="swiper_image" />
             <div class="small_type"><span>益智</span><span>小游</span><span>24</span></div>
            <div classs="small_bg" id="small_slide">
             <div class="small_con">
             <p><i>开心消消乐</i><em>English</em></p>
             <span>开发者：消消乐</span>
             </div>
            </div>
        </div>
      </div>
    </div>
      <div class="swiper-button-prev"><img src="@/assets/img/icon_prev.png" border="none"></div>
    <div class="swiper-button-next"><img src="@/assets/img/icon_next.png"  border="none"></div>
    </div>
    
    
  </div>
</div>
</template>


<script>
import Swiper from 'swiper';
import 'swiper/css/swiper.min.css';
 export default {
    name: 'carrousel',
    data() {
      return {
       current:1,
        lists: [
				{
         
					title: "全部游戏",
					en: "All Game"
				},
				{
					title: "小游戏",
					en: "Small Game"
				},
        {
					title: "H5页游",
					en: "H5 Game"
				},
        {
					title: "单机APK",
					en: "console Game"
				},
			],
        swiperOptionTop: {
          grabCursor: true,
           slideToClickedSlide: true,
            autoplay:true,
            loop:true,
            clickable :true,
            effect : 'fade',
          pagination: {
                  el: ".swiper-pagination",
                  bulletClass: "swiper-pagination-bullet",
                  bulletActiveClass: "swiper-pagination-bullet-active"
                },

        },
        swiperOptionThumbs: {
          slidesPerView: 7,
          spaceBetween: 28,
          slideToClickedSlide: true,
          grabCursor: true,
          loop:true,
          touchRatio: 0.2,
          freeMode: true,
          centeredSlides : true,
          navigation: {
            nextEl: '.swiper-button-next',
            prevEl: '.swiper-button-prev'
          },
        },
        imgTop:[
          {
            name:"开心消消乐",
            imgUrl:require("@/assets/img/big_1.jpg"),
            enlish:"English name",
            des:"休闲",
            desc:"益智",
            dev:"开发者：消消乐"
          },
          {
            name:"阳台2",
            imgUrl:require("@/assets/img/bg_2.jpg")
          },
          {
            name:"阳台3",
            imgUrl:require("@/assets/img/bg_3.jpg")
          }
        ],
        imgThumbs:[
          {
            name:"阳台4",
            imgUrl:require("@/assets/img/bg_4.jpg")
          },
          {
            name:"阳台5",
            imgUrl:require("@/assets/img/bg_5.jpg")
          },
          {
            name:"阳台6",
            imgUrl:require("@/assets/img/bg_6.jpg")
          }
          ,
          {
            name:"阳台7",
            imgUrl:require("@/assets/img/bg_5.jpg")
          },
          {
            name:"阳台8",
            imgUrl:require("@/assets/img/bg_3.jpg")
          },
          {
            name:"阳台9",
            imgUrl:require("@/assets/img/bg_2.jpg")
          },
          {
            name:"阳台10",
            imgUrl:require("@/assets/img/bg_6.jpg")
          },
          
          
        ]
      } 
    },
   methods:{			
	
		},	   
	  mounted: function() {}  

  }


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.selectedColor{
         color:#4b7dff;
        background-color: #f6f6f6;
    }
.slide_bg{
  width: 100%;
 background:rgba(11, 45, 70, 0.7);
  z-index: 10;
  position: absolute;
  bottom:0;
  border-radius: 8px 8px 0 0;
  overflow: hidden;
  height: 152px;
  transition:height 0.3s;
	-webkit-transition:height 0.3s; 
}
.gallery-top .swiper-slide:hover .slide_bg{
  height:100%;
}
.gallery-top .swiper-slide:hover .go{
  display:block;
}
.slide_txt{
  position: absolute;
  bottom: 0;
  color: #fff;
  width: 100%;
  padding: 12px 0;
}
.slide_top{
  margin: 0 40px ;
}
.slide_title{
  overflow: hidden;
  margin-bottom: 5px;
}
.slide_title span{
font-size: 28px;
font-weight: bold;
float: left;
cursor: default;
}
.slide_title span em{
  font-size: 16px;
  font-weight: normal;
  margin-left: 8px;
  cursor: default;
  font-style: normal;
  opacity:0.8;

}
.go{
  position: absolute;
  display: inline-block;
  height:40px;
  line-height:40px;
  background:#ccc;
  color:#fff;
  top:50%;
  left:50%;
  transform: translate(-50%, -50%);  
  background-color: #0ba7d4;
  padding:0 12px;
  border-radius:20px;
  font-size:20px;
  font-weight:bold;
  padding:0 31px;
  box-shadow: 0px 2px 6px 0px rgba(11, 167, 212, 1);
  border: 1px solid rgba(255, 255, 255, 0);
  z-index:11;
  opacity:1;
  display:none;
 
}
.go:hover{
  text-decoration:none;
  color:#fff;
}

.go img{
  vertical-align:middle;
  margin-left:6px;
  width:20px;
  height:20px;
  margin-top:-1px;
}


.slide_title  i{
  float: right;
  display: inline-block;
  height: 24px;
  line-height: 24px;
  background: #0ba7d4;
  padding: 0 8px;
  font-size: 14px;
  font-style: normal;
  border-radius: 4px;
  margin-top: 4px;
  cursor: default;
box-shadow: 0px 2px 6px 0px rgba(0, 0, 0, 0.4);
border: 1px solid rgba(255, 255, 255, 0);
}
.slide_title  i em{
  font-size: 14px;
  font-style: normal;
  font-style:14px;
  border-radius: 5px;
  cursor: default;
}
.slide_title  i em+em{
  margin-left:8px;
}
.slide_dep {
  overflow: hidden;
}
.slide_dep em{
 
  font-size: 14px;
  font-style: normal;
  font-weight: normal;
   opacity:0.8;

}
.slide_dep span{
  float: right;

}
.slide_dep  strong+strong{
  margin-left: 20px;
  display: inline-block;
   opacity:0.8;

}
#slide_dep  strong i{
  width:16px;
  height:16px;
  display:inline-block;
  margin-right:4px;

}
#slide_dep  strong i img{
  vertical-align:middle;
}

.slide_bor{
  border-top:1px solid #fff ;
  width: 100%;
  height: 1px;
  opacity: 0.1;
  margin: 10px 0 13px 0;
}
.slide_bot{
  margin: 0 40px;
 
}
.slide_bot em{
  float: left;
  font-size: 12px;
  font-style: normal;
   opacity:0.8;
}
.slide_bot span{
  float: left;
  display: inline-block;
  font-size: 12px;
  margin-left: 6px;
  width: 814px;
  line-height: 20px;
   opacity:0.6;
}
#small_slide{
  width: 100%;
  position:absolute;
  bottom:-4px;
  z-index:10;
  height:74px;
  background:rgba(11, 45, 70, 0.6)
}
.small_type{
  position:absolute;
  top:64px;
  margin:0 20px;
}
.small_type span{
  display:inline-block;
  height:16px;
  line-height:16px;
  background:#0BA7D4 ;
  color:#fff;
  font-size:10px;
  padding:0 6px;
  border-radius:5px;
}
.small_type span+span{
  margin-left:10px;
}
.small_con{
  margin:0 20px;
}
.small_con p{
  margin:10px 0 8px 0;
}
.small_con p i{
  font-size:16px;
  font-weight:bold;
  color:#fff;
  font-style:normal;

}
.small_con p  em{
  font-size:10px;
  color:#fff;
  margin-left:5px;
  opacity:0.6;
  font-style:normal;
}
.small_con span{
  font-size:12px;
  color:#fff;
  opacity:0.6;
  font-style:normal;
}
.small_horz{
  position:relative;
  margin:0 54px;

}
   .gallery-top {
      height:540px;
      width: 960px;
      margin-top:70px;
      margin-bottom:70px;
    }

    .gallery-thumbs .swiper-slide {
      width: 220px ;
      height: 100%;
     
    }
    .gallery-thumbs .swiper-slide img {
      width: 100%;
      height: 90px;
     
    }
    .gallery-thumbs .swiper-slide-active {
  
      border:1px solid #0B2D46 ;
    
border-radius: 10px 10px 0px 0px;
box-shadow: 0px 2px 6px 0px rgba(0, 0, 0, 0.4);
    }
    .gallery-thumbs .swiper-slide-active img {
  
     opacity:0.5;
    }
    .gallery-thumbs .swiper-slide-active #small_slide {
  
        background:rgba(11, 45, 70, 1)

    }
  
  

.swiper-slide{
  overflow: hidden;

}
.gallery-top .swiper-slide{

  width:960px;
  height: 540px;
  border-radius: 8px;
  position:relative;
}
.gallery-top img.swiper_img{
  width:960px;
  height: 540px;
   border-radius: 8px;

}
.gallery-thumbs{
  margin: 0 54px;
}
.gallery-thumbs .swiper-wrapper{

}
.gallery-thumbs .swiper-slide{
  
  height: 160px;
  border-radius: 8px;
}
.gallery-thumbs img.swiper_image{
  width:100%;
  height: 160px;
  border-radius: 8px;
}
#pag_ida .my-bullet {
    width: 8px;
    height: 8px;
    display: inline-block;
    border-radius: 100%;
    background: #000;
  
}
.swiper-button-prev, .swiper-button-next{
  width: 36px;
  height: 36px;
  display:block;
  
}
.swiper-button-prev, .swiper-button-next:active{
  border:none;
  
}
.swiper-button-prev, .swiper-button-next img{
  width: 36px;
  height: 36px;
  
}
.swiper-button-next, .swiper-container-rtl .swiper-button-prev{
  right:0;
}
.swiper-button-prev, .swiper-container-rtl .swiper-button-next{
  left:0;
}
.swiper-button-prev:after, .swiper-container-rtl .swiper-button-next:after{
  display:none;
}
.swiper-button-next:after, .swiper-container-rtl .swiper-button-prev:after {
     display:none;
}
#pag_slide{
  bottom:5px;
}
#pag_slide span.swiper-pagination-bullet{
  background:#fff !important;
}
#pag_slide  .swiper-pagination-bullet-active{
  background:#FF0BA7D4 !important;
}
#pag_slide.swiper-pagination-bullet{
  margin:0 10px;
}
</style>