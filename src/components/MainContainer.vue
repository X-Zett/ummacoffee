<script setup>
import { computed } from 'vue';
import { useRouter, useRoute } from 'vue-router';

const router = useRouter();
const route = useRoute();

// Автоматически определяем активный роут
const activeRoute = computed(() => route.path);

function navigateTo(route) {
  router.push(route);
}
</script>


<template>
  <div class="mainCon fixed flex bottom-8 left-0 right-0 w-fit px-3 py-2 m-auto justify-center gap-5 bg-white z-10 shadow-2xl border-[1px]">
    <div class="tab" :class="{ active: activeRoute === '/' }" @click="navigateTo('/')">
      <svg style="" width="20" height="20" fill="transparent" stroke="black" version="1.1" viewBox="0 0 24 24" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g id="info"/><g id="icons"><path d="M23.6,10.3L13.2,2.4c-0.7-0.5-1.7-0.5-2.5,0L0.4,10.3C-0.4,10.9,0,12,1,12h1v6.1C2,20.2,3.8,22,6,22h2   c0.6,0,1-0.4,1-1v-4.9C9,15,9.9,14,11,14h2c1.1,0,2,1,2,2.1V21c0,0.5,0.4,1,1,1h2c2.2,0,4-1.8,4-3.9V12h1   C23.9,12,24.3,10.9,23.6,10.3z" id="home"/></g></svg>
    </div>
    <div class="tab" :class="{ active: activeRoute === '/menu' }" @click="navigateTo('/menu')">
      <svg style="" width="20" height="20" fill="transparent" stroke="black" version="1.1" viewBox="0 0 24 24" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g id="info"/><g id="icons"><g id="block"><path d="M8,2H4C2.9,2,2,2.9,2,4v4c0,1.1,0.9,2,2,2h4c1.1,0,2-0.9,2-2V4C10,2.9,9.1,2,8,2z"/><path d="M20,2h-4c-1.1,0-2,0.9-2,2v4c0,1.1,0.9,2,2,2h4c1.1,0,2-0.9,2-2V4C22,2.9,21.1,2,20,2z"/><path d="M8,14H4c-1.1,0-2,0.9-2,2v4c0,1.1,0.9,2,2,2h4c1.1,0,2-0.9,2-2v-4C10,14.9,9.1,14,8,14z"/><path d="M20,14h-4c-1.1,0-2,0.9-2,2v4c0,1.1,0.9,2,2,2h4c1.1,0,2-0.9,2-2v-4C22,14.9,21.1,14,20,14z"/></g></g></svg>
    </div>
    <div class="tab" :class="{ active: activeRoute === '/cart' }" @click="navigateTo('/cart')">
      <svg style="" width="20" height="20" fill="transparent" stroke="black" version="1.1" viewBox="0 0 24 24" xml:space="preserve" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><g id="info"/><g id="icons"><g id="cart2"><circle cx="10" cy="20" r="2"/><circle cx="16" cy="20" r="2"/><path d="M21.6,7.8C21.2,7.3,20.6,7,20,7H8.6L8,3.6C7.8,2.7,7,2,6,2H4C2.9,2,2,2.9,2,4s0.9,2,2,2h0.3L6,14.4c0.2,1,1,1.6,2,1.6h10    c0.9,0,1.6-0.6,1.9-1.4l2-5C22.1,9,22,8.4,21.6,7.8z"/></g></g></svg>
    </div>
  </div>

  <router-view />
</template>

<!--#405147-->
<!--#1f2b27-->
<style scoped>
.mainCon {
  border-radius: 50px;
}

.tab {
  cursor: pointer;
  transition: background-color 0.3s ease;
  padding: 10px;
  border-radius: 10px;
}

.tab.active {
  background-color: #333333;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  border-radius: 100%;
}

.tab.active svg {
  stroke: #ffffff;

}

b {
  color: white;
  font-size: 13px;
  margin-left: 12px;
  margin-right: 12px;
}
</style>
