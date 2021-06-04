<template>
  <div class="cards__item" v-bind:class="{readed: item.readed}"> 
    <div>
      <label>
        Прочтено
        <input type="checkbox" v-on:change="item.readed = !item.readed">
      </label>
      
      <h3 class="cards__item__header">{{item.title}}</h3>
      <p>{{item.description}}</p>
      <p style="text-align:right" class="cards__item__category">Категория: {{item.category}}</p>
      <button class="cards__item__button-delete" v-on:click="$emit('remove_item', item.id)">
        удалить
      </button>
    </div>
  </div>  
</template>
<style scoped>
  .readed {
    opacity: 0.5;
  }
</style>
<script>
  export default {
    props:{
      item:{
        type: Object,
        required: true
      }
    }
  }

</script>