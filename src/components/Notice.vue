<template>
  <!-- 보여주기위해서 relative -->
  <!-- 공지 -->
  <div class="max-w-6xl mx-auto px-[2%] my-5 relative">
    <div class="border bg-white md:shadow-md rounded-2xl">
      <ul class="flex md:gap-x-10 p-5 py-0">
        <li class="basis-[20%] md:basis-[15%] text-xs sm:text-sm md:text-base py-5 text-center transition-all duration-500 rounded-br-2xl rounded-bl-2xl cursor-pointer" v-for="(e,index) in NoticeNav" :key="e" @click="TabSelectIndex = index" :class="TabSelectIndex === index && 'font-bold bg-[#0088cc] text-white'">
          <!-- a태그 눌렀을때 상단으로 올라가는 기능이 기본으로 탑재되있는데 그거를 막아주는 기능이다. vue에서는 @click.prevent -->
          <a href="#" @click.prevent>{{ e }}</a>
        </li>
      </ul>
      <div class="flex justify-between px-5 mt-4">
        <!-- e안써주는이유? -->
        <ul v-for="(e,index) in NoticeTabContent" :key="index" class="first-of-type:overflow-hidden first-of-type:mr-4 sm:mr-0">
          <li v-for="(el,i) in e" :key="i" class="py-5 last-of-type:mb-3 text-xs sm:text-sm md:text-base">
            <a href="#" @click.prevent class="flex flex-wrap items-center">
              <img v-if="index === 0" :src="require(`@/assets/images/icon_water.png`)" alt="아이콘" class="h-full mr-3 hidden sm:inline-block">
              <!-- overflow-hidden text-ellipsis whitespace-nowrap 3개 있어야 동작 줄이면 ... 으로  -->
              <span class="overflow-hidden text-ellipsis whitespace-nowrap">{{ el }}</span>
            </a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
import NoticeData from "../assets/Data.json"
export default {
  name:"NoticePage",
  data(){
    return{
      NoticeNav:NoticeData.Notice.Nav,
      NoticeContent: NoticeData.Notice.Content,
      TabSelectIndex : 0
    }
  },
  //notice 탭 메뉴
  computed:{
    NoticeTabContent(){
      return this.NoticeContent[`Notice_${this.TabSelectIndex}`].filter(data => data)
      //오브젝트의 경우 배열로 이름을 출력
      // return console.log(this.NoticeContent)
      // return console.log(this.NoticeContent["Notice_1"])
    }
  }
}
</script>
<style>
  
</style>