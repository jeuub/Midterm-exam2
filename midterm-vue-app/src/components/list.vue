<template>
  <div class="cards">
    <item v-for="item in items" :key="item" 
    v-bind:item="item"
    v-on:remove_item="remove_item"
    />
    <div class="cards__addcard">
      <form @submit.prevent="onSubmit">      
      <label>
        Название
        <input type="text" v-model="card_title">
      </label>
      <label>
        содержание
        <input type="text" v-model="card_text">
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
    data(){
      return{
        card_title:'',
        card_text:'',
        
      }
    },
    methods: {
      remove_item(id){
        this.$emit('remove_item', id);
      },
      onSubmit(){

        if (this.card_title.trim&&this.card_text){
          const newItem = {
          id: Date.now(),
          title: this.card_title,
          description: this.card_text,
          readed: false,
          }
          this.$emit('addItem', newItem)
        }
        
      }
    }
  }
</script>

