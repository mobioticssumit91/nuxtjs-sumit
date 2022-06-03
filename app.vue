<template>
  <div>
     <swiper
    :slides-per-view="5"
    :space-between="10"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  > 

    <swiper-slide v-for="(i, key) of dataset" :key="key">
        <img :src="i.images[1].url" />
     </swiper-slide>
  
  </swiper>


    <swiper
    :slides-per-view="5"
    :space-between="10"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  > 

    <swiper-slide v-for="(i, key) of dataset" :key="key">
        <img :src="i.images[1].url" />
     </swiper-slide>
  
  </swiper>


  <swiper
    :slides-per-view="5"
    :space-between="10"
    @swiper="onSwiper"
    @slideChange="onSlideChange"
  > 

    <swiper-slide v-for="(i, key) of dataset" :key="key">
        <img :src="i.images[1].url" />
     </swiper-slide>
  
  </swiper>

  <!-- <iframe src="https://noorplay.com" style="height:1200px;width: 100vw;" title="Iframe Example"></iframe> -->

  </div>
</template>


<script>
 // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';
export default {
  data() {
    return {
      test : [100, 200],
      dataset: []
    }
  },
   components: {
      Swiper,
      SwiperSlide,
    },
    setup() {
      const onSwiper = (swiper) => {
        console.log(swiper);
      };
      const onSlideChange = () => {
        console.log('slide change');
      };
      return {
        onSwiper,
        onSlideChange,
      };
    },
  mounted () {
    var requestOptions = {
      method: 'GET',
      redirect: 'follow'
    };

  fetch("https://api.cloud.altbalaji.com/zuul/catalogue/balaji/catalogue/filters/all-shows?domain=IN&size=10&page=2", requestOptions)
    .then(response => response.json())
    .then(result => {

        this.dataset = result.content

  
	
      })
    .catch(error => console.log('error', error));
  }
}
</script>

<style>

</style>
