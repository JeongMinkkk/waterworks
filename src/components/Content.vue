<template>
  <div class="bg-[#e1edff]">
     <div class="max-w-6xl mx-auto flex flex-wrap py-24 pb-10 px-[2%]">
      <!-- swiper -->
      <swiper :modules="Modules" :autoplay="{delay: 3000}" :slides-per-view="1" :space-between="10" :loop="true" :navigation="{prevEl:'.swiper-button-prev',nextEl:'.swiper-button-next'}" :pagination="{clickable:true, type:'fraction'}" class="basis-full md:basis-[56%] text-xs md:text-sm ml-0">
        <swiper-slide v-for="(e,index) in 5" :key="index">
          <img :src="require(`@/assets/images/slide_${index+1}.jpg`)" :alt="e" class="w-full h-full">
        </swiper-slide>
        <div class="swiper-button-prev hidden after:content-['prev'] after:md:text-4xl after:sm:text-2xl sm:block"></div>
        <div class="swiper-button-next hidden after:content-['next'] after:md:text-4xl after:sm:text-2xl sm:block"></div>
        <!-- 스타일 따로 설정 -->
        <div class="swiper-pagination"></div>
      </swiper>
      <div class="basis-full md:basis-5/12 bg-white rounded-tl-2xl rounded-br-2xl p-10 text-center mt-5 md:mt-0">
        <p class="font-bold text-2xl">민원문의는 달구벌콜센터</p>
        <div class="flex justify-center my-5">
          <img :src="require(`@/assets/images/icon_call.png`)" alt="콜센터">
          <h2 class="font-extrabold text-5xl ml-3">053-120</h2>
        </div>
        <p class="rounded-2xl bg-[#40acff] w-52 mx-auto py-1 text-white text-xl">평일(월 ~ 금)</p>
        <p class="my-5 font-bold text-xl">08:00 ~ 22:00</p>
        <p class="rounded-2xl bg-[#40acff] w-52 mx-auto py-1 text-white text-xl">토 / 일 / 공휴일</p>
        <p class="my-5 font-bold text-xl">09:00 ~ 18:00</p>
      </div>
      <div class="basis-full mt-5">
        <ul class="flex flex-wrap justify-between">
          <li v-for="(e,index) in ContentMenu[0]" :key="e" class="bg-white rounded-tl-2xl rounded-br-2xl text-center basis-[48%] sm:basis-[23.5%] py-8 md:shadow-md" :class="index >= 2 && 'mt-5 sm:mt-0'">
            <a href="#" @click.prevent>
              <img :src="require(`@/assets/images/icon_${ContentMenu[1][index]}.png`)" :alt="e" :title="e" class="mx-auto h-14">
              <!-- 오류가 떴는데 Data.json과 이미지파일명이 맞지않았다.대문자 -->
              <p class="font-bold text-sm sm:text-lg mt-3">{{e}}</p>
            </a>
          </li>
        </ul>
      </div>
      <div class="basis-full my-5">
        <img :src="require(`@/assets/images/long-banner.jpg`)" alt="배너" class="w-full">
      </div>
      <div class="basis-full flex justify-between flex-wrap">
        <div v-for="e in ContentSelectBox" :key="e" class="basis-full md:basis-[32.5%] mb-5 last-of-type:mb-0">
          <select class="w-full px-5 py-2 border rounded">
            <option v-for="el in e" :key="el" :value="el">{{ el }}</option>
          </select>
        </div>
      </div>
     </div>
  </div>
</template>
<script>
import ContentData from "../assets/Data.json"
// swiper
import {Swiper,SwiperSlide} from 'swiper/vue'
import {Navigation, Pagination, Autoplay} from 'swiper'
import 'swiper/css'
import 'swiper/css/bundle';
import 'swiper/css/pagination';
import 'swiper/css/navigation'


export default {
  name:"ContentPage",
  data(){
    return{
      ContentMenu : ContentData.ContentMenu,
      Modules : [Navigation, Pagination, Autoplay],
      ContentSelectBox: ContentData.SelectBox
    }
  },
  components:{
    Swiper,
    SwiperSlide
  }
}
</script>
<style>
  .swiper-pagination{
    background: rgba(255, 255, 255, 0.5);
    padding: 2px;
    letter-spacing: 3px;
    width: 15%;
    border-radius: 20px;
    left: 80%;
    margin-bottom: 10px;
  }
</style>