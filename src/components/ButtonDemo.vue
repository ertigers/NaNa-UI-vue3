<template>
  <div>
    <Button @click="log">点击这里</Button>
    <Button @click="log" theme="button">点击这里</Button>
    <Button @click="log" theme="link">点击这里</Button>
    <Button @click="log" theme="text">点击这里</Button>
  </div>
</template>

<script>
import Button from '../lib/Button.vue'
export default {
  components:{ Button },
  setup() {
    const log = ()=>{
      console.log("点击了，打印一下")
    }
    return { log }
  }
}
</script>