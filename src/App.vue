<template>
  <from @submit.prevent="AddToCard">
    <label>Текст</label>
    <input  
      type="text" 
      v-model="msg"
      placeholder="Введите текст"/>
    <input 
      type="submit"
      @click="AddToCard"
      >
  </from>
 
  <ul>
    <li v-if="items.length === 0">Тут нечего нет</li>
    <li 
      v-for="item in items" 
      :key="item.id">
        {{ item.msg}}
      <button @click="deleteApp(item.id)">Удалить</button>  
      </li>
  </ul>
</template>
 
<script setup>
import { ref } from 'vue'
 
const msg = ref('');
const items = ref([])
 
const AddToCard = () => {
  if(msg.value.trim() === '') {
    alert("Введите текст")
    return
  }
 
  items.value.push({
    id: Date.now(),
    msg: msg.value.trim()
  })
 
}
 
const deleteApp = (id) => {
  items.value = items.value.filter(item => item.id !== id)
}
</script>
 
<style scoped>
 
ul > li {
 
  list-style: none;
}
</style>