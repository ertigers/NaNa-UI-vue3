<template>
  <div>Dialog 示例</div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="visible" 
          :closeOnClickOverlay="false" 
          :ok="f1" :cancel="f2">
    <template v-slot:title>
      <h1>笨鸟</h1>
    </template>
    <template v-slot:content>
      <h3>znn</h3>
      <h3>是</h3>
      <h3>傻鸟</h3>
      <h3>至少笨鸟还会先飞</h3>
    </template>
  </Dialog>
  <h1>示例2</h1>
  <Button @click="showDialog">openDialog</Button>
</template>

<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue'
import {openDialog} from '../lib/openDialog'
import { ref,h } from 'vue';
export default {
  components:{
    Dialog,Button
  },
  setup() {
    const visible = ref(false)
    const closeOnClickOverlay = ref(false)
    const toggle = ()=>{
      visible.value = !visible.value      
    }
    const f1 = ()=>{
      return false
    }
    const f2 = ()=>{
      return false
    }
    const showDialog = () => {
      openDialog({
        title: h('strong', {}, '标题'),
        content: '你好',
        ok() {
          console.log('ok')
          return false
        },
        cancel() {
          console.log('cancel')
          return false
        },
        closeOnClickOverlay: false
      })
    }
 
    return { 
      visible,closeOnClickOverlay,
      toggle,f1,f2,showDialog }
  }
  
}
</script>