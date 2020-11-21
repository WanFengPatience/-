<template>
  <div>
    <div class="header_banner">
      <div class="layout">
        <div class="closeBtn" @click="closeHeader()"></div>
      </div>
    </div>
    <div class="shortcut">
     <div class="layout">
        <div class="s-sub">
          <ul>
            <li :class="item.isDrop? 's-dropdown' : ''" v-for="(item,index) in shortcutLeftList" :key="index">
              {{item.isDrop ?  '' : item.title}}
              <div class="h" v-if="item.isDrop">
                <a href="javascript:void(0)" class="icon-dropdown">
                  {{item.title_more}}
                </a>
              </div>
              <div class="b" v-if="item.isDrop">
                <div :class="item.isDrop ? 'content1': ''">
                  <ul>
                    <li v-for="(title,index) in item.content" :key="index">{{title}}</li>
                  </ul>
                </div>
                <div :class="item.isIconDrop ? 'content2' : ''" v-show="item.isIconDrop"></div>
              </div>
            </li>
          </ul>
        </div>
        <div class="s-main">
          <ul>
            <li  v-for="(item,index) in shortcutRightList" :key="index">
              <div :class="item.isDrop? 's-dropdown' : ''">
                {{item.isDrop ?  '' : item.title}}
                <div class="h" v-if="item.isDrop">
                  <a href="javascript:void(0)" class="icon-dropdown">
                    {{item.title_more}}
                  </a>
                </div>
                <div class="b c" v-if="item.isDrop">
                  <div :class="item.isDrop ? 'content11': ''">
                  <ul>
                    <li v-for="(title,index) in item.content" :key="index">{{title}}</li>
                  </ul>
                  </div>
                  
                  <!-- 网站导航 -->
                  <div :class="item.isIconDrop ? 'content2' : ''" v-show="item.isIconDrop">
                     <div class="navs-icon">
                     <a  v-for="(item,index) in daohangList.sy" :key="index">
                     <span style="font-size:0;"> </span>
                     {{item}}
                     </a>
                    </div>
                 <div class="fl" style="width:185.0px;margin-top:22.0px;margin-bottom:20.0px;">
                   <div class="bold f16 black" style="margin-bottom:8.0px;" v-for="(item,index) in daohangList.list1" :key="index">{{item}}</div>
                   <div>
                     <div class="fl" style="width:80.0px;overflow:hidden;margin-bottom:4.0px;"  v-for="(item,index) in daohangList.list2" :key="index">
                       <a href="javascript:void(0)" class="icon-dropdown">{{item}}</a>
                     </div>
                  </div>
                 </div>

                  <div class="fl" style="width:185.0px;margin-top:22.0px;margin-bottom:20.0px;">
                   <div class="bold f16 black" style="margin-bottom:8.0px;" v-for="(item,index) in daohangList.list3" :key="index">{{item}}</div>
                   <div>
                     <div class="fl" style="width:80.0px;overflow:hidden;margin-bottom:4.0px;"  v-for="(item,index) in daohangList.list4" :key="index">
                       <a href="javascript:void(0)" class="icon-dropdown">{{item}}</a>
                     </div>
                  </div>
                 </div>

                <div class="fl" style="width:185.0px;margin-top:22.0px;margin-bottom:20.0px;">
                   <div class="bold f16 black" style="margin-bottom:8.0px;" v-for="(item,index) in daohangList.list5" :key="index">{{item}}</div>
                   <div>
                     <div class="fl" style="width:80.0px;overflow:hidden;margin-bottom:4.0px;"  v-for="(item,index) in daohangList.list6" :key="index">
                       <a href="javascript:void(0)" class="icon-dropdown">{{item}}</a>
                     </div>
                  </div>
                 </div>

                <div class="fl" style="width:185.0px;margin-top:22.0px;margin-bottom:20.0px;">
                   <div class="bold f16 black" style="margin-bottom:8.0px;" v-for="(item,index) in daohangList.list7" :key="index">{{item}}</div>
                   <div>
                     <div class="fl" style="width:80.0px;overflow:hidden;margin-bottom:4.0px;"  v-for="(item,index) in daohangList.list8" :key="index">
                       <a href="javascript:void(0)" class="icon-dropdown">{{item}}</a>
                     </div>
                  </div>
                 </div>
            </div>
          <!-- 手机版 -->
          <div :class="item.isIconDrop1 ? 'content3' : ''" v-show="item.isIconDrop1">
               <div class="clearfix dropdown-code-detail">  
                 <a href="#">
                   <img class="code-img" :src="picList.image1">
                 </a>
                 <div class="code-info">
                   <h2><p v-for="(item,index) in picList.list1" :key="index">{{item}}</p></h2>
                   <p v-for="(item,index) in picList.plist1" :key="index" class="red">{{item}}</p>
                     <p v-for="(item,index) in picList.plist3" :key="index" class="red">{{item}}</p>
                   <span class="icon-andrid fl mgr-5"></span>
                   <span class="icon-ios fl mgr-5"></span>
                   <span class="icon-wechat fl"></span>
                 </div>  
               </div>    
               <div class="clearfix dropdown-code-detail">     
                  <a><img class="code-img" :src="picList.image2"></a>  
                  <div class="code-info">       
                  <h2><p v-for="(item,index) in picList.list2" :key="index">{{item}}</p></h2>
                  <p v-for="(item,index) in picList.plist2" :key="index">{{item}}</p>
                  <span class="icon-wechat"></span>   
                  </div>    
                </div>   
                <div class="clearfix dropdown-code-detail"> 
                   <a><img class="code-img" :src="picList.image3"></a> 
                   <div class="code-info">  
                   <h2><p v-for="(item,index) in picList.list3" :key="index">{{item}}</p></h2>
                   <span class="icon-wechat"></span>  
                   </div>    
                   </div> 
                </div>
             </div>
              </div>

             <div :class="item.isIcon? 's-dropdownIcon' : ''" v-if="item.isIcon">
                <div class="h" v-if="item.isIcon">
                  <a
                    href="javascript:void(0)"
                    class="icon-dropdown"
                  >{{item.title_icon}} ({{count()}})</a>
                </div>
                <div class="b" v-if="item.isIcon">
                  <div :class="item.isIcon ? 'content1': ''" v-show="item.isIcon">
                    <p class="cartIcon">
                      <span></span>
                    </p>
                       <p class="cartInfo">
                          {{item.title_cart}}
                       </p>
                  </div>
                  <div :class="item.isIconDrop ? 'content2' : ''" v-if="item.isIconDrop"></div>
                </div>
              </div>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div class="header">
      <div class="layout">
        <div class="left">
          <div class="logo">
            <img :src="logoList.logo_image" alt="" width="205px" height="36px">
          </div>
          <div class="naver">
            <ul>
              <li><img :src="logoList.icon_1" alt=""></li>
              <li><img :src="logoList.icon_2" alt=""></li>
              <li class="title" v-for="(item,index) in logoList.title" :key="index">{{item}}</li>

            </ul>
          </div>
        </div>
        <div class="right">
          <div class="search">
            <input type="text">
            <span class="iconfont icon-search">&#xe603;</span>
            <div class="search-key">
              <p v-for="(item,index) in logoList.search_key" :key="index">{{item}}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Header',
  data () {
    return {
      shortcutLeftList: [
        {
          title: '首页'
        },
        {
          title: '华为官网'
        },
        {
          title: '荣耀官网'
        },
        {
          title: '花粉俱乐部'
        },
        {
          title: 'V码(优购码)'
        },
        {
          title: '企业购'
        },
        {
          title: 'Select Region'
        },
        {
          title_more: '更多精彩',
          isDrop: true,
          isIconDrop: false,
          content: [
            'EMUI',
            '应用市场',
            '华为终端云空间',
            '开发者联盟'
          ]
        }
      ],
      shortcutRightList: [
        {
          title: '请登录',
          isLink: true
        },
        {
          title: '注册',
          isLink: true
        },
        {
          title: '我的订单'
        },
        {
          title_more: '客户服务',
          // isDrop: true,
          // content1: true,
          // content: {}
          isDrop: true,
          isIconDrop: false,
          content: [
            '服务中心',
            '联系客服'
          ]
        },
        {
          title_more: '网站导航',
          isDrop: true,
          isIconDrop: true
        },
        {
          title_more: '手机版',
          isDrop: true,
          isIconDrop1: true
        },
        {
          title_icon: '购物车',
          isDrop: false,
          isIcon: true,
          title_cart: "您的购物车是空的，赶紧选购吧~",
          // $store: this.$store
        }
      ],
       daohangList:{
         sy: [
          '商城首页'
        ],
        list1: [
          '频道'
        ],
        list2: [
         '华为专区','荣耀专区','企业购'
        ],
        list3: [
           '产品'
        ],
        list4: [
          '手机','笔记本','平板','智能穿戴','智慧家居','智能屏','耳机音箱','热销配件','生态产品','增值服务'
        ],
        list5: [
           '增值服务'
        ],
        list6: [
           '以旧换新','补购保障','一口价换电池'
        ],
        list7: [
           '会员'
        ],
        list8: [
           '会员频道'
        ],
      },
      picList: {
        image1:'https://res.vmallres.com/pimages//pages/cdnImages/FWETOIrFlCrX4xuB8E16.png',
        image2:'https://res.vmallres.com/pimages/sale/2018-11/20181116180507506.jpg',
        image3:'https://res.vmallres.com/pimages//sale/2018-12/6Y7SW4v4hnJ9kl9fDC9d.jpg',
        list1: ['华为商城'],
        plist1: ['新人专享好礼'],
        plist3: ['最高5000积分'],
        list2: ['华为商城公众号'],
        plist2: ['微信扫一扫'],
        list3: ['微信小程序']
      },
      logoList: {
        logo_image: 'https://res.vmallres.com/pimages//common/config/logo/SXppnESYv4K11DBxDFc2.png',
        icon_1: 'https://res.vmallres.com/pimages//navigation/icon/GrguiqzHENWVYHYWyHBM.png',
        icon_2: 'https://res.vmallres.com/pimages//navigation/icon/AHwTUFRpDSQyuIZ7tLJz.png',
        title: [
          '华为 P40 系列',
          '荣耀30系列',
          '安心居家'
        ],
        search_key: [
          'P40',
          '荣耀30'
        ]
      }
    }
  },
  methods: {
    closeHeader () {
      const headerBanner = document.getElementsByClassName('header_banner')[0]
      headerBanner.style.display = 'none'
    }
  },
  computed: { // 计算属性
    count () {
      return () => this.$store.state.cart
    }
  }
}
</script>
<style scoped>
@import url(../static/css/header1.css);
@import url(../static/css/iconfont.css);
</style>
