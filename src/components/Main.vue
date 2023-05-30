<template>
  <div class="relative">
    <img :src="require(`@/assets/images/main_bg.png`)" alt="메인배경" class="absolute top-0 w-full h-full lg:h-auto">
    <div class="max-w-6xl mx-auto px-[2%]">
      <!-- 검색창 -->
      <!-- 너무 떨어져있다싶음 높이값 여기서 수정 -->
      <div class="w-full relative flex justify-center items-center h-72 sm:h-96 sm:visible invisible">
        <div class="w-3/5 lg:w-2/4 md:w-3/5 relative">
          <input type="text" placeholder="검색어를입력해주세요" class="w-full border text-[#287db1] placeholder:text-[#287bd1] border-[#287db1] rounded-2xl p-3 text-sm font-bold">
          <img :src="require(`@/assets/images/icon_search_blue.png`)" alt="검색" class="absolute top-3 right-3 w-6 m-0">
        </div>
      </div>
      <!-- 자주찾는서비스 -->
      <!-- 영역이 absolute 라서 배경이 기준이 되어있기 때문에 relative-->
      <div class="text-center font-bold relative text-2xl">
        <h3 class="font-extrabold">자주찾는 서비스</h3>
        <div class="bg-white my-6 rounded-tl-2xl rounded-br-2xl border sm:shadow-md">
          <ul class="flex flex-wrap justify-around my-5 transition-all duration-75">
            <!-- <li v-for="i in 8" :key="i"><img :src="require(`@/assets/images/fav_0${i}.png`)" alt="자주찾는서비스"></li>
            <li v-for="e in Service" :key="e" class="text-sm">{{ e }}</li> -->
            <!-- 비트윈은 살짝 영역이 안맞아서 베이시스 줌  -->
            <li v-for="(e,index) in Service" :key="e" class="py-4 text-center basis-1/4 lg:basis-auto ">
              <a href="#">
                <!-- 이미지mx-auto줘야 센터로 옴 -->
                <img :src="require(`@/assets/images/fav_0${index+1}.png`)" :alt="e" :title="e" class="mx-auto">
                <p class="text-xs sm:text-sm mt-4">{{ e }}</p>
              </a>
            </li>
          </ul>
        </div>
        <!-- 요금조회/민원신청/수질정보 -->
        <div class="w-full">
          <ul class="flex justify-between flex-wrap">
            <li v-for="(e,index) in ServiceMenu" :key="e" class="h-32 basis-full mb-5 sm:mb-0 sm:basis-[32%] bg-white border rounded-2xl md:shadow-md">
              <!-- items-center 세로길이값이 없으면 동작하지않는다  -->
              <a href="#" class="flex items-center py-5 h-full">
                <img :src="require(`@/assets/images/menu_0${index+1}.png`)" :alt="e" :title="e" class="mx-auto w-16">
                <p class="text-base md:text-xl mt-4 basis-8/12">{{ e }}</p>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ServiceData from '../assets/Data.json'
export default {
  name:"MainPage",
  data(){
    return{
      Service : ServiceData.Service,
      ServiceMenu : ServiceData.ServiceMenu,

    }
  }
}
</script>
<style>
  
</style>