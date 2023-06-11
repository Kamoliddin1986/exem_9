<template>
    <div class="w-[255px] h-screen flex flex-col text-[24px]  bg-[#363740] align-center">
      <div class="my-[38px] w-[100%] text-center">
        <h1 class="font-[700] text-[45px] text-white">Admin</h1>
      </div>
  
      <div class="flex flex-col gap-2 ml-[34px]">
        <nuxt-link :to="el.link" v-for="el in navLink" :key="el.id" class="mb-[34px]"
          ><Icon :name="el.icon"  class="text-[#DDE2FF]"/>
          <span class="text-[17px] ml-[25px] text-[#DDE2FF] text-[16px] font[600]">{{ el.title }}</span></nuxt-link
        >
      </div>
    </div>
  </template>
  
  <script setup></script>
  
  <style lang="" scoped></style>
  