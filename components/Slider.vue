<template>
  <div >
    <swiper
                    :slides-per-view="slidesPerView"
                    :space-between="20"
                    :pagination="{ clickable: true }"
                    :scrollbar="{ draggable: true }"
                    @swiper="onSwiper"
                    @slideChange="onSlideChange"

        :navigation="true" :modules="modules" class="mySwiper"
    >
      <swiper-slide> <Card></Card></swiper-slide>
      <swiper-slide> <Card></Card></swiper-slide>
      <swiper-slide> <Card></Card></swiper-slide>
      <swiper-slide> <Card></Card></swiper-slide>
      ...
    </swiper>
  </div>

</template>
<script>
// import Swiper core and required modules
import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';
import 'swiper/css/pagination';

// Import Swiper styles
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Pagination],
    };
  },
  mounted() {
    console.log('mounted', window.innerWidth)
  },
  computed: {
    slidesPerView() {
      if (window.innerWidth < 600)
        return 1
      if (600 < window.innerWidth) {
        if (window.innerWidth < 800) {
          console.log('2',  window.innerWidth)
          return 2
        }
      }
      return 3
    }
  }

};
</script>

<style lang="scss">
.collaborate-page-content {
  max-width: 950px;
  margin: 2.5rem auto;
}

//html, body {
//  width: 100%;
//  height:100%;
//}
//
//body {
//  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
//  background-size: 400% 400%;
//  animation: gradient 15s ease infinite;
//}
//
//@keyframes gradient {
//  0% {
//    background-position: 0% 50%;
//  }
//  50% {
//    background-position: 100% 50%;
//  }
//  100% {
//    background-position: 0% 50%;
//  }
//}
</style>
