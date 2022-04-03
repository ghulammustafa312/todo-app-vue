<template>
  <input type="text" class="form-control add-todo" placeholder="Add todo" v-model="title" @keyup.enter="saveTask(title)" />
</template>

<script>
import EventBus from '../EventBus';
export default {
	name: 'AddTodo',
    data(){
        return { 
            title:''
        }
    },
    methods:{
        saveTask(title){
            EventBus.$emit('add-todo',{title,id:Date.now().toString(),completed:false})
            this.title=""
        }
    }
};
</script>

<style>
</style>
