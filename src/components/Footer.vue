<template lang="">
  <div class="max-w-6xl mx-auto px-[2%] py-5">
    <div class="flex flex-wrap items-center justify-between">
      <div class="basis-full md:basis-auto">
        <img :src="require(`@/assets/images/footer_logo.png`)" alt="로고" class="mx-auto">
      </div>
      <ul class="flex gap-x-5 mt-5 md:mt-0 justify-center basis-full md:basis-auto">
        <li v-for="e in FooterMenu" :key="e">
        <a href="#" @click.prevent class="text-xs sm:text-sm md:text-base">{{e}}</a></li>
      </ul>
      <ul class="flex text-xs sm:text-sm md:text-base flex-wrap basis-full justify-center text-gray-900 my-2">
        <!-- 줄였을때는 줄바꿈 되고 늘렸을때는 자동으로 옆으로 -->
        <!-- 줄였을때 ㅣ 이 선 처리야해야햐 -->
        <li class="relative after:absolute after:w-0.5 after:h-2/4 after:bg-black after:-right-2 after:top-2/4 after:-translate-y-2/4 basis-full text-center md:basis-auto mr-2">(42423) 대구광역시 남구 명덕로 52길 6-3 (이천동)</li>
        <li class="mr-2 md:ml-2 relative after:absolute after:w-0.5 after:h-2/4 after:bg-black after:-right-2 after:top-2/4 after:-translate-y-2/4">전화 053-670-2000</li>
        <li class="ml-2">팩스 053-670-2119</li>
      </ul>
      <p class="text-center basis-full text-xs sm:text-sm md:text-base text-gray-500">Copyright © Daegu Water. All Rights Reserved.</p>
    </div>
  </div>
</template>
<script>
export default {
  name:"FooterPage",
  data(){
    return{
      FooterMenu:["개인정보처리방침","법령정보","뷰어프로그램"]
    }
  }
}
</script>
<style>
  
</style>