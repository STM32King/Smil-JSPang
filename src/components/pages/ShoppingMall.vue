<template>
  <div>
    <div class="search-bar">
      <van-row>
        <van-col span="3" class="">
          <img :src="locationIcon" width="80%" class="location-icon" />
        </van-col>
          <van-col span="16" class="">
            <input type="text" class="search-input">
        </van-col>
            <van-col span="5" class="">
              <van-button size="mini">查找</van-button>
            </van-col>
      </van-row>
    </div>
    <!--swiper area-->
    <div class="swiper-area">
      <van-swipe :autoplay="1000">
        <van-swipe-item v-for="( banner ,index) in bannerPicArray" :key="index">
          <img v-lazy="banner.imageUrl" width="100%"/>
        </van-swipe-item>
      </van-swipe>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      msg: 'Shopping Mall ',
      locationIcon: require('../../assets/images/location.png'),
      bannerPicArray: [
        { imageUrl: require('../../assets/images/1.png') },
        { imageUrl: require('../../assets/images/2.png') },
        { imageUrl: require('../../assets/images/3.png') },
      ]
    }
  },
}
</script>

<style lang='scss'>
.search-bar {
  height: 2.2rem;
  background-color: #e5017d;
  line-height: 2.2rem;
  width: 100%;
  overflow: hidden;
}
.search-input {
  width: 100%;
  height: 1.3rem;
  border-top: 0px;
  border-left: 0px;
  border-right: 0px;
  border-bottom: 1px solid #ffffff !important;
  background-color: #e5017d;
  color: #fff;
}
.location-icon {
  padding-top: 0.2rem;
  padding-left: 0.3rem;
}
.swiper-area {
  width: 20rem;
  clear: both;
  max-height: 15rem;
  overflow: hidden;
}
</style>