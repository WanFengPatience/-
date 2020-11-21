<template>
  <el-carousel height="550px" indicator-position="outside">
    <el-carousel-item v-for="(item,index) in mainBannerList" :key="index">
      <img :src="item" alt="">
    </el-carousel-item>
  </el-carousel>
</template>

<script>
export default {
  data () {
    return {
      mainBannerList: [
        'https://res.vmallres.com/pimages//pages/picImages/39663229269512236693.png',
        'https://res.vmallres.com/pimages//pages/picImages/89757980269518975798.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/84407097369519070448.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/81575097369519057518.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/68012197369519121086.jpg',
        'https://res.vmallres.com/pimages//pages/picImages/89757980269518975798.jpg'
      ]
    }
  }
}
</script>
<style>
  /* .el-carousel__item h3 {
    color: #475669;
    font-size: 18px;
    opacity: 0.75;
    line-height: 300px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
    background-color: #99a9bf;
  }

  .el-carousel__item:nth-child(2n+1) {
    background-color: #d3dce6;
  } */

  .el-carousel__indicators {
    position: absolute !important;
    bottom: 60px !important;
    right: 120px;
    z-index: 10 !important;
  }
  .el-carousel__button {
    width: 10px !important;
    height: 10px !important;
    float: left;
    border-radius: 50%;
    border: 1px solid #FFFFFF;
    margin: 0 3px;
  }
  .el-carousel__indicators--outside button {
    background-color: blue;
  }
  .el-carousel__arrow--left {
    left: 23% !important;
    width: 60px !important;
    height: 60px !important;
    font-size: 20px !important;
  }
  .el-carousel__arrow--right {
    right: 10% !important;
    width: 60px !important;
    height: 60px !important;
    font-size: 20px !important;
  }
  .el-carousel__item img{
    width: 100%;
    height: 550px;
  }
</style>
