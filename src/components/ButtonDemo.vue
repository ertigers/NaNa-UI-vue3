<template>
  <div>
    <Button @click="log" size="small">
      点击这里
    </Button>
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