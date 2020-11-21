<template>
  <div class="main">
    <div class="main-banner">
      <div class="layout">
        <MainBannerImage></MainBannerImage>
        <div class="category">
          <ul class="category-ul">
            <li v-for="(item, index) in selectTab" :key="index">
              <div class="category-item">
                <div class="category-info">
                  <a href="javascirpt:void(0)">
                    <span>{{item.title}}</span>
                  </a>
                </div>
              </div>
              <div class="category-panels" v-if="true" :style="item.widthStyle">
                <ul v-for="(select,selectIndex) in item.content" :key="selectIndex" :style="select.widthStyle">
                  <li v-for="(selectInner,index) in select.content" :key="index">
                      <a class="p-img" href="" v-if="!selectInner.isMore">
                        <img :src="selectInner.img" alt="">
                        <p>
                          <span>{{selectInner.title}}</span>
                        </p>
                      </a>
                      <a class="more" href="" v-if="selectInner.isMore">{{selectInner.more_title}}</a>
                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </div>
        <div class="login">
          <ul>
            <li class="fl s1">
              <div class="unlogin">
                <div class="fl w-name">
                  <img src="https://res.vmallres.com/20200630/images/echannel/misc/img_not_logged_in.png" alt="">
                </div>
                <div class="fl">
                  <div class="login-url">
                    您好！<a href="javascript:void(0)">登录</a> <span>&nbsp;/&nbsp;</span> <a href="javascript:void(0)">注册</a>
                  </div>
                  <div class="w-btn">
                    <a class="new" href="javascript:void(0)">新人福利</a>
                    <a href="javascript:void(0)">会员频道</a>
                  </div>
                </div>
              </div>
            </li>
            <li class="fl s2">
              <ul>
                <li v-for="(item,index) in navList" :key="index">
                  <div class="p-img">
                    <img :src="item.img" alt="" :style="item.style">
                  </div>
                  <p class="title">{{item.title}}</p>
                </li>
              </ul>
            </li>
            <li class="fl s3">
              <div class="notice">
                <p class="icon-notice">公告</p>
                <p class="notice-content">
                  <ul :style="noticeUlMarginTop">
                    <li v-for="(item,index) in noticeList" :key="index">{{item}}</li>
                  </ul>
                </p>
              </div>
              <div class="info">
                <ul>
                  <li v-for="(item,index) in navIconList" :key="index">
                    <a href="javascript:void(0)">
                      <span><img :src="item.img" alt="" :style="item.style"></span>
                      {{item.content}}
                    </a>

                  </li>
                </ul>
              </div>
            </li>
          </ul>
        </div>
        <div class="bg-slide"></div>
      </div>
    </div>
  </div>
</template>
<script>
import MainBannerImage from '@/components/MainBannerImage.vue'
export default {
  name: '',
  data () {
    return {
      navList: [
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          title: '企业购特惠',
          style: 'left: -150px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          title: '会员领券',
          style: 'left: -190px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          title: '以旧换新',
          style: 'left: -230px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          title: 'P40 Pro+',
          style: 'left: -270px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          title: '华为数码',
          style: 'left: -310px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          title: '荣耀数码',
          style: 'left: -350px'
        }
      ],
      noticeList: [
        '荣耀超级会员日活动公告',
        'HUAWEI 麦芒9 系列5G新品预订公告',
        '关于新疆受疫情管控升级对物流时效和服务影响的公告',
        '华为礼遇粉丝日活动公告',
        'Gentle Monster-HUAWEI智能眼镜晒单活动公告',
        '荣耀超级会员日活动公告'
      ],
      noticeUlMarginTop: 'margin-top: 0px',
      navIconList: [
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          content: '优购码',
          style: 'left: -390px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          content: '更换电池',
          style: 'left: -410px'
        },
        {
          img: 'https://res.vmallres.com/pimages//squaredInfo/icon/5/32b46fe090fcab93c1459eae921a2119.png',
          content: '补购保障',
          style: 'left: -430px'
        }
      ],
      selectTab: [
        {
          title: '手机',
          content: [
            {
              content: [
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/plqBwqiWNT7w3S1oHify.png',
                title: '华为MateBook系列'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/RfnzRjvwIx1VTVm8xHfk.png',
                title: '华为MateBook X系列'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/tDI1s1C6u0UNK3kpjX35.png',
                title: '华为MateBook D系列'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/w1o5IBLA7nNHhuMb2wTl.png',
                title: '华为MagicBook系列'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/hTG8axcpAcm4rlc953p1.png',
                title: '华为MagicBook Pro系列'
              }
              ],
            },
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/J0jm7RuLopoqLL6j9nWc.png',
                  title: '荣耀 V系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/BcIFunByzSBaydhI8X8T.png',
                  title: '荣耀 HONOR系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/1NS2TBQr6a8EXKAJ8L4y.png',
                  title: '荣耀 X系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/RekgcFmB36D9LlwLKmtt.png',
                  title: '荣耀 Play系列'
                },
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
          widthStyle: 'width: 488px; padding-left: 20px;'
        },
        {
          title: '笔记本',
          widthStyle: 'width: 488px; padding-left:20px',
          content: [
            {
              content: [
                {
                    img: 'https://res.vmallres.com/pimages//pages/frontCategory/RfnzRjvwIx1VTVm8xHfk.png',
                    title: '华为MateBook X系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/tDI1s1C6u0UNK3kpjX35.png',
                  title: '华为MateBook D系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/w1o5IBLA7nNHhuMb2wTl.png',
                  title: '华为MagicBook系列'  
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/hTG8axcpAcm4rlc953p1.png',
                  title: '华为MateBook B系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/w1o5IBLA7nNHhuMb2wTl.png',
                  title: '荣耀MagicBook系列'
                }
              ]
            },
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/hTG8axcpAcm4rlc953p1.png',
                  title: '荣耀MagicBook Pro系列'
                },
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
        },
        {
          title: '平板',
          widthStyle: 'width: 488px; padding-left:20px',
           content: [
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/SoXonWnoeMUuz9KZRGyw.png',
                  title: '华为MatePad系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/8wlL4vrACOekn5kexj47.jpg',
                  title: '荣耀 V系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/8wlL4vrACOekn5kexj47.jpg',
                  title: '华为畅想系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/LgNX0tnzWTb8Mu3xanaG.png',
                  title: '荣耀数字系列'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/6bQtXCQDRZ8480l6N1Eo.png',
                  title: '荣耀畅玩系列'
                }
              ]
            },
            {
              content: [
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
        },
        {
          title: '智能穿戴&VR',
           widthStyle: 'width: 488px; padding-left:20px',
          content: [
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/bvJbZEMQTr1qy29qnvxZ.png',
                  title: '智能手表'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/sYl3EZsnaJp74kySK0uW.png',
                  title: '儿童手表'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/Op9zTFnetpE2UBz72lZ6.png',
                  title: '智能手环'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/7rB1eW3yTzlmsJxUhz4o.png',
                  title: 'V R'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/svCuLCsIylj3EagzlFJm.png',
                  title: '智能健康配件'
                }
              ]
            },
            {
              content: [
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
        },
        {
          title: '智能家居',
           widthStyle: 'width: 488px; padding-left:20px',
        content: [
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/CSkYxTgopbtV6bLHOxWq.png',
                  title: '智能路由'
                },
                {
                 img: 'https://res.vmallres.com/pimages//pages/frontCategory/httvqlH4j44xjH2Fkoeb.png',
                 title: '移动路由'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/eXsJchzxTzKRTnevFe0r.png',
                  title: '智能音响'
                },
                {
                   img: 'https://res.vmallres.com/pimages//pages/frontCategory/G1jaM3KiE5xuF7x0YZ7g.png',
                  title: '智能存储'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/DJsv7p3cchO5rb1BawwY.png',
                  title: 'HiLink生态'
                }
              ]
            },
            {
              content: [
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
        },
        {
          title: '智慧屏',
          widthStyle: 'width: 242px',
         content: [
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/jCygCJMv6ginekIsCBmu.png',
                title: '华为智慧屏'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/jCygCJMv6ginekIsCBmu.png',
                title: '荣耀智慧屏'
                },
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
        },
        {
          title: '耳机音箱',
           widthStyle: 'width: 488px; padding-left:20px',
          content: [
            {
              content: [
                {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/uMozRHKrVE2rb5X95pGr.jpg',
                title: '真无线耳机'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/8GZSNEOIyFTlKHGXJIUp.jpg',
                title: '有线耳机'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/Q4tB9qli0N2lI9aqbnUB.jpg',
                title: '蓝牙耳机'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/OArxm5z1VxtyOcsuNGWN.png',
                title: '蓝牙音箱'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/DeNI79kOsHbW8IXBE7Rh.png',
                title: '智能眼镜'
              }
              ]
            },
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/ponGt6tOncpW9tyJZhwC.png',
                title: '智能音箱'
                },
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            }
          ],
        },
        {
          title: '配件',
          widthStyle: 'width: 788px; padding-left:20px',
        content: [
            {
              content: [
               {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/iXXgaQhk3RhRNcb3dUhX.png',
                title: '充电器/线材'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/iXXgaQhk3RhRNcb3dUhX.png',
                title: '移动电源'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/UkPqRhFdsfuw0Mgon0lW.png',
                title: '自拍杆/支架'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/e7VsKW9NLDvxDXhBMFZD.png',
                title: '摄像机/镜头'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/AGwf96xPj4cLuL3dpJ1G.png',
                title: '智能硬件'
                }
              ]
            },
            {
              content: [
                {
                img: 'https://res.vmallres.com/pimages//pages/navigation/B7R6qLbvn8J6DbwODyWS.png',
                title: '生活周边'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/navigation/RyT80PAF3dD0VUy9XTgz.png',
                title: '保护壳'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/navigation/nxlajbLtHHaH00OhSaAv.png',
                title: '保护套'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/navigation/UWVgAL2WFNeoVHZRRE8s.png',
                title: '贴膜'
                },
                {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/Xqw5avmFrpr7LGyNTZE0.png',
                title: '个人电脑配件'
                }
              ]
            },

            {
              content:[
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/4PoI3AWlpGikrJtR0gfY.png',
                title: '平板配件'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/oYGaqUtNyOAa8gj1a3Pc.png',
                title: '智慧屏配件'
              },
              {
                img: 'https://res.vmallres.com/pimages//pages/navigation/ecDhrcKmmX2lMEJ6EWUN.png',
                title: '穿戴配件'
              },
              {
                isMore: true,
                more_title: '查看更多'
              }
              ]
            }
          ],
        },
        {
          title: '生态产品',
          widthStyle: 'width: 788px; padding-left:20px',
          content: [
            {
              content: [
               {
                  img: 'https://res.vmallres.com/pimages//pages/navigation/0fiZED1M3bzCZCtrmVuv.png',
                  title: '智能灯光'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/iR28UGaUlGGtocEkV5vg.png',
                  title: '生活电器'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/CjXb7nAKCcLrhloNO14u.png',
                  title: '数码周边'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/Hbh7GYts0Ye1ozqXQsqC.png',
                  title: '环境卫士'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/U8DruLnlMn8Mn4l8ankk.png',
                  title: '安防门锁' 
                }
              ]
            },
            {
              content: [
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/RJO1wsBU6rsbJeXf0kAl.png',
                  title: '健康保障'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/gGcXeKvu6bIKZUwMJhuK.png',
                  title: '运动健身'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/5Rf9Nz2tA6T0Hl7LQVGn.png',
                  title: '户外出行'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/Su3PP0R5phG77pi2PjHs.png',
                  title: '厨电卫浴'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/pAQE9qGrvT2kYOGERdmr.png',
                  title: '影音娱乐'
                }
              ]
            },

            {
              content:[
              {
                img: 'https://res.vmallres.com/pimages//pages/frontCategory/isXiE0yeEU46E2DolmYs.png',
                title: '个护美妆'
              },
              {
                isMore: true,
                more_title: '查看更多'
              }
              ]
            }
          ],
        },
        {
          title: '增值服务和其他',
           widthStyle: 'width: 242px; padding-left:20px',
          content: [
            {
              content: [
               {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/ZQnJL2WVUmZvVDkFIDRE.png',
                  title: '华为视频卡'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/druWEKy6zCanbd02FQhl.png',
                  title: '花币卡'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/qTEFwRvC8TEQ6qyHvIoB.png',
                  title: '华为音乐卡'
                },
                {
                  img: 'https://res.vmallres.com/pimages//pages/frontCategory/8J0Q5RpbK23FoBD4nX2h.png',
                  title: '电池更换服务'
                },
                {
                  isMore: true,
                  more_title: '查看更多'
                }
              ]
            },
          ],
        }
      ],
      mainBannerList: [
        'https://res.vmallres.com/pimages//pages/picImages/39663229269512236693.png',
        'https://res.vmallres.com/pimages//pages/picImages/89757980269518975798.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/84407097369519070448.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/81575097369519057518.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/68012197369519121086.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/89757980269518975798.jpg'
      ],
      interval: null,
      index: -1 // 用于确定当前轮播图下标
    }
  },
  methods: {
    test () { // 公告轮播
      var test = 0
      setInterval(() => {
        this.noticeUlMarginTop = 'margin-top:' + (0 - 43 * test) + 'px'
        test++
        if (test === 6) {
          test = 0
        }
      }, 1000)
    }
  },
  mounted () { // 在页面加载完成后调用
    this.test()
  },
  components: {
    MainBannerImage
  }
}
</script>
<style scoped>
@import url("../static/css/MainBanner1.css");
</style>
