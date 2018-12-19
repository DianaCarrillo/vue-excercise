<template>
 <div>
   <input type="text" v-model="todo" v-on:keyup.enter="sending" />
   <button @click="sending(todo)">ok</button>
   <div class="card container offset-lg-5" style="width: 18rem;" v-for="(item, index) in arrayList" :key="item.id">
    <ul class="list-group list-group-flush" >
     <!-- <li class="list-group-item">{{todo}}</li> -->
     <li class="list-group-item" > {{index}}. {{item}}</li> 
     <button class="done-task" @click="doneTask(index)">Done<i class="fas fa-check-circle"></i></button>     
     <button class="delete-task" @click="deleteTask(index)">Delete<i class="fas fa-times-circle"></i></button>
    </ul>
   </div>
 </div>
</template>

<script>
 export default {
     name: 'inputTodo',
     data() {
       return {
         todo: "",
         arrayList: []
       }
     },
     methods : {
       sending : function (){
         this.arrayList.push(this.todo)
         this.todo = "";
     
        },
        doneTask : function (index){
          alert('congrats, you have done your task'+ ' ' + index)
        },
        deleteTask : function (index){
        var confirm = window.confirm('Do you really want to erase your task?')
          if(confirm === true){
            // console.log('delete this', index);
            this.arrayList.splice(index, 1)
        } else{
          return;
          }

        }
     }
 }
</script>

<style>
    .card {
        margin-top: 30px;
    }
    i{
    margin: 10px;
    }
    .done-task {
      margin-bottom: 5px;
      background-color:greenyellow;
      border-color: greenyellow;
    }
    .delete-task {
      background-color:red;
      border-color:red;
    }
</style>
