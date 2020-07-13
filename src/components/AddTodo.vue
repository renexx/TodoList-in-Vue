<template>
    <div>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="What are you planning?" class="taskInput">
            <input type="submit" value="ADD" class="btn">
        </form>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
    name:"AddTodo",
    data(){
        return {
            title:""
        }
    },
    methods:{
        addTodo(e){
        e.preventDefault();
        
            const newTodo = {
                id: uuidv4(),
                title:this.title,
                completed:false
            }
            //send up to parent
            this.$emit('add-todo',newTodo);
            this.title="";
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
    max-width: 1140px;
    width: auto;
    margin: 0 auto;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
  .taskInput{
      margin: 10px 0 10px 0;
      padding:10px;
      width:180px;
      height:40px;
      border-radius: 15px 0 0 15px;
      border:1px solid #dbdbdb;
      border-right: none;
      outline: none;
      font-size: 18px;
  }
  .btn{
      width:60px;
      height:40px;
      margin: 10px 0 10px 0;
      background-color: #f7b71b;
      color:white;
      border:none;
      border-radius: 0 15px 15px 0;
      outline: none;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.2s ease-in-out;
  }
  .btn:hover{
      background-color: #ffa600;
  }
</style>