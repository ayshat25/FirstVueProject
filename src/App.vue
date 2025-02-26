<template>
  <h3>{{ info }}</h3>
  <p>{{ someInfo }}</p>

  <button type="button" @click="this.info = 'Some new '">Отправить</button>
</template>

<script>
export default {
  data(){
    return{
      info: 'Title!',
      someInfo: 'Anons some message'
    }
  }
}
</script>

<style>
  h3{
    font-weight: lighter;
  }

  p{
    color: red;
  }
</style>
