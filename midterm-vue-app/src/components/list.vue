<template>
  <div class="cards">
    <item v-for="item in items" :key="item" 
    v-bind:item="item"
    v-on:remove_item="remove_item"
    />
    <div class="cards__addcard">
      <form @submit="onSubmit">      
      <label>
        Название
        <input type="text" v-model="card-title">
      </label>
      <label>
        содержание
        <input type="text" v-model="card-text">
      </label>
      <select>
        <option v-for="category in categorys" :key="category"> {{category.name}}</option>
      </select>
      <button class="cards__addcard__button" type>
        добавить карточку
      </button>
      </form>
    </div>
  </div>
</template>
<script>
  import item from '@/components/item';
  export default {
    props:['items', 'categorys'],
    components:{
      item 
    },
    methods: {
      remove_item(id){
        this.$emit('remove_item', id);
      },
      
    }
  }
</script>

