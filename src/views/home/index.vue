<template>
  <div class="home">
    <img src="@/assets/vue.svg" class="vue" alt="Vue logo"/>
    <div class="title">Vue3 + Ts + Vite</div>
    <div class="logos">
      <a href="https://vitejs.dev" target="_blank">
        <img src="@/assets/vite.svg" class="logo" alt="Vite logo"/>
      </a>
      <a href="https://pinia.web3doc.top/" target="_blank">
        <img src="https://pinia.web3doc.top/logo.svg" class="logo pinia" alt="Pinia logo"/>
      </a>
      <a href="https://vuejs.org/" target="_blank">
        <img src="@/assets/vue.svg" class="logo" alt="Vue logo"/>
      </a>
      <a href="https://vueuse.org/">
        <img src="https://d33wubrfki0l68.cloudfront.net/2f6479d73bc25170dc532dd42e059166573bf478/61057/favicon.svg" class="logo vueuse" alt="VueUse logo" />
      </a>
    </div>
    <div class="pinia">
      <div>{{counter}}</div>
      <button @click="increment">Increment</button>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { useStore } from '@/store/index'
import { storeToRefs } from 'pinia'
const store = useStore()
const { counter } = storeToRefs(store)
const { increment } = store
</script>

<style lang="less" scoped>
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100%;
  margin-top: 60px;
  .vue {
    width: 150px;
    margin-bottom: 20px;
  }
  .title {
    font-size: 60px;
    margin-bottom: 20px;
  }
  .logos {
    margin-bottom: 20px;
    .logo {
      height: 50px;
      padding: 8px;
      will-change: filter;
    }

    .logo:hover {
      filter: drop-shadow(0 0 10em white);
        scale: 1.3;
      }
  }
  .pinia {
    text-align: center;
    button {
      margin-top: 10px;
    }
  }
}
</style>
