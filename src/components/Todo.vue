<template>
<div class="container">
    <div class="row">
        <div class="col-md-6">
            <div class="todolist not-done">
             <h1>Todos</h1>
                <input type="text" @keyup.enter="addToTodo" v-model="newTodo" class="form-control add-todo" placeholder="Add todo">
                    <button id="checkAll" class="btn btn-success" @click="markAllCompleted">Mark all as done</button>

                    <hr>
                    <ul id="sortable" class="list-unstyled">

                      <li class="ui-state-default" v-for="(todo,index) in todoList.filter(todo => !todo.completed)" :key="index">
                        <div class="checkbox">
                            <label>
                            <input type="checkbox" :checked="todo.completed ? true : false" @change="markCompleted(todo)" />
                              {{todo.title}}
                            </label>
                        </div>
                    </li>
                </ul>
                <div class="todo-footer">
                    <strong><span class="count-todos"></span></strong> Items Left {{remaining}}
                </div>
            </div>
        </div>
        <div class="col-md-6">
            <div class="todolist">
             <h1>Already Done</h1>
                <ul id="done-items" class="list-unstyled">

                    <li v-for="(todo,index) in todoList.filter(todo => todo.completed)" :key="index">{{todo.title}}
                      <button @click="removeTodo(index)" class="remove-item btn btn-default btn-xs pull-right"><span class="glyphicon glyphicon-remove"></span></button>

                    </li>

                </ul>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
  name: "Todo",
    data () {
    return {
      newTodo: '',
      idForTodo: 1,
      todoList: []
    }
  },
  computed: {
    remaining(){
      return this.todoList.filter(todo => !todo.completed).length
    }
  },
  methods: {
    addToTodo(){
      if (this.newTodo.trim() == ''){
        return
      }
      this.todoList.push({
        id: this.idForTodo,
        title: this.newTodo,
        completed: false,
      })
      this.newTodo = ''
      this.idForTodo++
    },
    removeTodo(index){
      this.todoList.splice(index, 1)
    },
    markCompleted(todo){
      todo.completed = true
    },
    markAllCompleted(){

    }
  }
}

</script>

<style>

body{
    background-color:#EEEEEE;
}
.todolist{
    background-color:#FFF;
    padding:20px 20px 10px 20px;
    margin-top:30px;
}
.todolist h1{
    margin:0;
    padding-bottom:20px;
    text-align:center;
}
.form-control{
    border-radius:0;
}
li.ui-state-default{
    background:#fff;
    border:none;
    border-bottom:1px solid #ddd;
}

li.ui-state-default:last-child{
    border-bottom:none;
}

.todo-footer{
    background-color:#F4FCE8;
    margin:0 -20px -10px -20px;
    padding: 10px 20px;
}
#done-items li{
    padding:10px 0;
    border-bottom:1px solid #ddd;
    text-decoration:line-through;
}
#done-items li:last-child{
    border-bottom:none;
}
#checkAll{
    margin-top:10px;
}

</style>
