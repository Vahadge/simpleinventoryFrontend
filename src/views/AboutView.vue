<template>
  <div class="about bg-[url('../src/assets/images/what-is-inventory.png')] z-10">
    
    <div class="w-screen h-screen bg-daily-dev-tips flex flex-col items-center justify-center
    bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 opacity-90">
      
      <p class="lg:text-6xl font-bold text-2xl m-5">freemium inventory solution for small business</p>      
      <p class="lg:text-3xl text-1xl m-6">-manage you business inventory and avail the basic features for free</p>
      <p class="lg:text-3xl text-1xl m-6">-Kickstart your business requirements</p>
      <p class="lg:text-3xl text-1xl m-6">-Avail now, pay later when you need</p>
      <div>
          <button @click="counter.increment()">-</button> {{ counter.count }}<button @click="counter.increment()">+</button>
        {{ auth.isAuthenticated }}
        <button @click="auth.logout()">Logout</button>
        
      </div>
      <div>{{ auth.IsEmployeeLoggedIn }}</div>
      <div><button @click="welcomeNote = 'Welcome again'">Change welcomenotes</button></div>
      <div>{{ welcomeNote }}</div>
      <div>{{ counter.doubleCount }}</div>
    </div>
  </div>
</template>
<script setup>
import {ref , watch, watchEffect} from "vue";
import { useCounterStore } from "@/stores/counter";
import {useAuthStore} from '@/stores/auth'

const welcomeNote = ref("Welcome");

const counter = useCounterStore();
const auth = useAuthStore();

watch(()=>welcomeNote.value, (val, newWelcomeNote)=>{
  console.log(`from watch ${newWelcomeNote}, ${newWelcomeNote}`);
}
);

watchEffect(() => {
  console.log(`from watch effect ${welcomeNote}`);
});


</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
