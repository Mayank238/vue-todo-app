<template>
    <div>
        <div class="row jumbotron">
            <div class="col-md-12">
                <div class="well">
                    <h2>Create a New Todo</h2>
                    <form>
                        <div class="form-group">
                            <label for="todoitem">Todo Item</label>
                            <input  type="text" v-model="input" class="form-control col-lg-6" id="todoitem" placeholder="Todo Item" @keyup.enter="add()"/>
                        </div>
                        <button type="button" v-on:click="add()" class="btn btn-primary">Create</button>
                    </form>
                </div>
            </div>
        </div>
        <div class="container row ">
            <div class="col-md-12">
                <h2>List</h2>
                <ul class="list-group">
                    <li v-for="(todo, index) in todos" :key="index" class="list-group-item">
                        <input type="checkbox" name=""
                        @change="changeEvent(index,todo.done)">
                         <span :class="{done: todo.done}">{{ todo.text }}</span>
                      <div class="text-right">
                          <button class="btn btn-danger" @click="delete1(index)">
                            <i class="fa fa-trash"></i>
                          </button>
                      </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Todo",
        data () {
            return {
                todos: [{text:'First one',done:false}],
                input: ""

            }
        },
        methods: {
            add() {
                this.todos.push({text: this.input, done: false});
                this.input = "";
            },
            delete1(event) {
                this.todos.splice(event, 1);
            },
            changeEvent(inx,value) {
               this.todos[inx].done = !value;
            },
             bind: function(a){
               // a.done = !a.done
              // console.log(a.done)
           },

        }
    }
</script>
<style>
.done{
    text-decoration-line: line-through;
    color: gray;
}

</style>
