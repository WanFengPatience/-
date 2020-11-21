<template>
  <div class="main">
    <div class="menu">
      <div class="layout">
        <ul >
          <li v-for="title in menulist" :key="title"><a href=""><img :src="title.img" alt=""></a></li>
        </ul>
      </div>
    </div>
    <div class="goods">
      <div class="layout">
        <h2>热销单品</h2>
        <div class="content">
          <ul >
            <li v-for="title in goodslist" :key="title">
              <a href="" :class="title.isTrue? 'img1' : ''" v-if="title.isTrue">
                <img :src="title.img" alt="">
              </a>
              <a href="" :class="title.isTrue? '' : 'img2'" v-if="!title.isTrue">
                <p class="p-img">
                  <img :src="title.img" alt="">
                </p>
                <p class="title">{{title.title}}</p>
                <p class="desc">{{title.desc}}</p>
                <p class="price">{{title.price}}</p>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
 
    <div class="goods2">
      <div class="layout">
        <div class="goods2-header" >
          <div class="left"  v-for="item in goods2headerlist" :key="item">
            <h2 v-if="!item.isDrop">{{item.title}}</h2>
            <ul v-for="title in item.content" :key="title">
              <li v-if="!item.isDrop"><a href="">{{title}}</a></li>
            </ul>
          </div>
          <div class="right" v-for="item in goods2headerlist" :key="item">
            <li v-if="item.isDrop" >
              <a href="">{{item.title_more}}<img :src="item.img" alt=""></a>
            </li>
          </div>
        </div>
        <ul>
          <li v-for="title in goods2list" :key="title">
              <a href="" :class="title.isTrue? 'img1' : ''" v-if="title.isTrue">
                <img :src="title.img" alt="">
              </a>
              <a href="" :class="title.isTrue? '' : 'img2'" v-if="!title.isTrue">
                <p class="p-img">
                  <img :src="title.img" alt="">
                </p>
                <p class="title">{{title.title}}</p>
                <p class="desc">{{title.desc}}</p>
                <p class="price">{{title.price}}</p>
              </a>
            </li>
        </ul>
      </div>
    </div>
    <div class="goods4">
      <div class="layout">
        <div class="goods2-header">
          <div class="left"  v-for="item in goods4headerlist" :key="item">
            <h2 v-if="!item.isDrop">{{item.title}}</h2>
            <ul v-for="title in item.content" :key="title">
              <li v-if="!item.isDrop"><a href="">{{title}}</a></li>
            </ul>
          </div>
          <div class="right" v-for="item in goods4headerlist" :key="item">
            <li v-if="item.isDrop" >
              <a href="">{{item.title_more}}<img :src="item.img" alt=""></a>
            </li>
          </div>
        </div>
        <ul>
          <li v-for="title in goods4list" :key="title">
              <a href="" :class="title.isTrue? 'img1' : ''" v-if="title.isTrue">
                <img :src="title.img" alt="">
              </a>
              <a href="" :class="title.isTrue? '' : 'img2'" v-if="!title.isTrue">
                <p class="p-img">
                  <img :src="title.img" alt="">
                </p>
                <p class="title">{{title.title}}</p>
                <p class="desc">{{title.desc}}</p>
                <p class="price">{{title.price}}</p>
              </a>
            </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: '',
  data () {
    return {
      menulist: [
        {
          img: 'https://res.vmallres.com/pimages//pages/picImages/73730068049516003737.jpg'
        },
        {
          img: 'https://res.vmallres.com/pimages//pages/picImages/GcsYv6B9jO5jZvHBjHm2.jpg'
        },
        {
          img: 'https://res.vmallres.com/pimages//pages/picImages/35790532249513509753.png'
        },
        {
          img: 'https://res.vmallres.com/pimages//pages/picImages/93809596549519590839.png'
        }
      ],
      goodslist: [
        {
          isTrue: true,
          img: 'https://res0.vmallres.com/pimages//frontLocation/content/30724137349513142703.png'
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6901443398027/428_428_C5B3EEB31BA081CF605FE04A1118DEF332F4C3003CC60ECEmp.png',
          title: 'HUAWEI P40 Pro+',
          desc: '享6期免息',
          price: '¥7988',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6901443391967/428_428_3F15B3F159FCB2929091EAD02F81B3E9156F0B2FE71F8433mp.png',
          title: '荣耀30',
          desc: '最高省310元|部分赠配件|免息 ',
          price: '¥2999',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6901443353361/428_428_6381399AD1BADEB91EBD63AF4EAE62016C58317DDEB7C5C4mp.png',
          title: 'HUAWEI Mate 30 5G',
          desc: '6期免息|赠多重好礼',
          price: '¥4499',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6972453165220/428_428_11B9905C1BEED75A300A7A6B70612208DAA32DE91D8F7372mp.png',
          title: '荣耀Play4',
          desc: '6400万锐力四摄',
          price: '¥1999',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6901443353279/428_428_F23055642D59B61C0038B9B6015570AC05A35A7E3838809Emp.png',
          title: 'HUAWEI Mate 30 Pro 5G',
          desc: '6期免息|赠多重好礼',
          price: '¥6399',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6972453164773/428_428_3350888FD6EA6D30D5F0E99DA3C0D0B15A3BD92523AF0F0Cmp.png',
          title: '荣耀X10 Max',
          desc: '享12期免息',
          price: '¥2099',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6972453164971/428_428_AEEDD8A45E7E18EA7F10E0386C1104EEB994C561C391C803mp.png',
          title: '华为畅享Z 5G',
          desc: '购机赠耳机',
          price: '¥2199',
          isTrue: false
        },
        {
          img: 'https://res0.vmallres.com/pimages//product/6901443386451/428_428_E008716749454F878551D09785164FA1DD1742C36857F752mp.png',
          title: '荣耀Play4T Pro',
          desc: '全系优惠110元',
          price: '¥1399',
          isTrue: false
        }
      ],
      goods2headerlist: [
        {
          title: '手机',
          content: [
            'HUAWEI Mate系列',
            'HUAWEI P系列',
            'HUAWEI nova系列',
            '华为畅享系列',
            '荣耀 V系列',
            '荣耀 HONOR系列',
            '荣耀 X系列',
            '荣耀 Play系列'
          ]
        },
        {
          isDrop: true,
          title_more: '查看更多',
          img: require('../static/images/youjiantou.png')
        }
      ],
      goods2list: [
        {
          isTrue: true,
          img: 'https://res0.vmallres.com/pimages//frontLocation/content/29131318249511313192.jpg'
        },
        {
          title: '荣耀 Play4T',
          desc: '整点购机赠耳机',
          price: '¥1199',
          img: 'https://res0.vmallres.com/pimages//product/6901443387731/428_428_1DB7D2A4E023F52DC64AE021E52A83F43BC0524BE4E0387Fmp.png'
        },
        {
          title: '华为畅享20 Pro',
          desc: '赠耳机|整点赠好礼',
          price: '¥1999',
          img: 'https://res0.vmallres.com/pimages//product/6972453165077/428_428_C089F3BE3BD266BAC2B777E1190F59241E0CE65223CA694Bmp.png'
        },
        {
          title: '荣耀30S 5G',
          desc: '8GB版本限量送耳机',
          price: '¥2399',
          img: 'https://res0.vmallres.com/pimages//product/6901443388141/428_428_AE2A1F00B7D98D94AAB55AD59800475D6ADFA000C71CA40Fmp.png'
        },
        {
          title: 'HAUWEI nove 5z',
          desc: '限量直降300',
          price: '¥1299',
          img: 'https://res0.vmallres.com/pimages//product/6901443356126/428_428_21A7667FA769CBD35B1B4977DF61F62E011DB64E3FDCA71Bmp.png'
        },
        {
          title: '荣耀Play4 Pro',
          desc: '最高优惠200',
          price: '¥2699',
          img: 'https://res0.vmallres.com/pimages//product/6972453162526/428_428_7E78427DAD528145F81C899480925B4A833C3793651A5B90mp.png'
        },
        {
          title: 'HAUWEI nove 7 Pro 5G',
          desc: '千玺主题日|赠更多好礼',
          price: '¥3699',
          img: 'https://res0.vmallres.com/pimages//product/6901443393039/428_428_7484AB32CD916B697FED5DE343A4384247FC1B9D7159B022mp.png'
        },
        {
          title: '荣耀9X',
          desc: '最高优惠400元',
          price: '¥1099',
          img: 'https://res0.vmallres.com/pimages//product/6901443321339/428_428_1563503515663mp.png'
        },
        {
          title: 'HUAWEI nove 7 5G',
          desc: '千玺主题日|赠更多好礼',
          price: '¥2999',
          img: 'https://res0.vmallres.com/pimages//product/6901443393251/428_428_7843929F829F1DAC9EFC6A50B6BD0CA9999BA351D2526117mp.png'
        },
        {
          title: '荣耀V30',
          desc: '最高优惠1010元',
          price: '¥2499',
          img: 'https://res0.vmallres.com/pimages//product/6901443360734/428_428_3FBC077CC886A1DF10E7F063D8F8C6B9083B641CE06CD0FEmp.png'
        },
        {
          title: 'HUAWEI Mate Xs 5G',
          desc: '科技新物种',
          price: '>¥16999',
          img: 'https://res0.vmallres.com/pimages//product/6901443376506/428_428_5A4871DB483B6E0D92CA527C3D367A6A32E2B433F5870412mp.png'
        },
        {
          title: '荣耀V30 PRO',
          desc: '优惠500 部分送配件',
          price: '¥3399',
          img: 'https://res0.vmallres.com/pimages//product/6901443356874/428_428_23726B2102572FFB2141D62293E8780F18D9861161FA67DCmp.png'
        },
        {
          title: '荣耀20青春版',
          desc: '最高优惠400',
          price: '¥999',
          img: 'https://res0.vmallres.com/pimages//product/6901443352531/428_428_37C267F23F1D9D8B7DBF9202529F8CFBB5AEACA87BCFF900mp.png'
        },
        {
          title: '华为畅享10 Plus',
          desc: '最高优惠200',
          price: '¥1399',
          img: 'https://res0.vmallres.com/pimages//product/6901443327690/428_428_50BAC6E20ED77CBBE6D44BD831603E6F0FB45173DB1EE8B2mp.png'
        },
        {
          title: '荣耀Play3',
          desc: '最高优惠310',
          price: '¥999',
          img: 'https://res0.vmallres.com/pimages//product/6901443330089/428_428_40B400F6978F30299BAEAD3FB31C97EF8694128D28B041A2mp.png'
        }
      ],
      goods4headerlist: [
        {
          title: '智慧屏',
          content: [
            '华为智慧屏',
            '荣耀智慧屏',
            
          ]
        },
        {
          isDrop: true,
          title_more: '查看更多',
          img: require('../static/images/youjiantou.png')
        }
      ],
      goods4list: [
        {
          isTrue: true,
          img: 'https://res0.vmallres.com/pimages//frontLocation/content/53869498149519496835.jpg'
        },
        {
          title: '荣耀智慧屏X1系列 65英寸',
          desc: '限时最高优惠300元 ',
          price: '¥2999',
          img: 'https://res4.vmallres.com/pimages//product/6901443401710/428_428_ED25171C4C0B9F13A7A71A08EC9CF6725DE9A173423463BAmp.png'
        },
        {
          title: '华为智慧屏V55i',
          desc: '特惠400+12期免息 ',
          price: '¥3399',
          img: 'https://res4.vmallres.com/pimages//product/6901443387588/428_428_1293C2C791F87BE0948D95135021BC202D4B20A735051BDFmp.png'
        },
        {
          title: '荣耀智慧屏X1系列 55英寸',
          desc: '限时最高优惠300元 ',
          price: '¥2199',
          img: 'https://res4.vmallres.com/pimages//product/6901443401703/428_428_C87EFEE1636151629AB635316B00DEF08ACF73EEB8864EAFmp.png'
        },
        {
          title: '华为智慧屏 V65',
          desc: '最高省1000+12期免息 ',
          price: '¥6599',
          img: 'https://res4.vmallres.com/pimages//product/6901443361557/428_428_9CA7B99629C486B82A64D8EBCCB6BF5BDB211AA893F42F55mp.png'
        },
        {
          title: '荣耀智慧屏X1系列 50英寸',
          desc: '限时最高优惠300元 ',
          price: '¥1979',
          img: 'https://res4.vmallres.com/pimages//product/6901443401956/428_428_9A49CD2E2A487CA47DC30109246CD63A185CE6C743E762B7mp.png'
        },
        {
          title: '华为智慧屏 V75',
          desc: '特惠1000+12期免息 ',
          price: '¥11999',
          img: 'https://res4.vmallres.com/pimages//product/6901443363834/428_428_F5914787EADD22E44AE873EB26A9DEE719BA467ACED12261mp.png'
        },
        {
          title: '荣耀智慧屏',
          desc: '最高优惠1530元 ',
          price: '¥2889',
          img: 'https://res4.vmallres.com/pimages//product/6901443293209/428_428_B8DB4FC62435E45B1298B4FE526708215AD7B75925C52421mp.png'
        },
        {
          title: '华为智慧屏X65',
          desc: '特惠400+12期免息 ',
          price: '¥24599',
          img: 'https://res4.vmallres.com/pimages//product/6901443390496/428_428_36F72EB747591D900CAC22B69D6537E1C04D5C485EB66BE0mp.png'
        }
      ]
    }
  }
}
</script>
<style scoped>
@import url("../static/css/main1.css");
</style>
