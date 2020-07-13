<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        
        <p>
            <input type="checkbox" @change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo',todo.id)" class="del"><i class="far fa-trash-alt"></i></button>
        </p>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
           this.todo.completed =!this.todo.completed;
        }
    }
}
</script>

<style scoped>
 .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc solid;
    max-width: 1140px;
    width: auto;
    margin: 0 auto;
   
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    
    color: rgb(145, 140, 140);
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
  del:hover{
      color:#ff0000;
  }
  .fa-trash-alt{
      font-size: 20px;
  }
  .fa-trash-alt:hover{
    color:#ff0000;
   
  }
  .fa-trash-alt:active{
    transform: translateY(3px);
  }

</style>