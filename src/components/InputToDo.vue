<template>
 <div>
   <input type="text" v-model="todo" v-on:keyup.enter="sending" />
   <button @click="sending(todo)">ok</button>
   <div class="card container offset-lg-5" style="width: 18rem;" v-for="(item, index) in arrayList" :key="item.id"  :style="{borderColor: activeColor}" >
    <ul class="list-group list-group-flush">
     <!-- <li class="list-group-item">{{todo}}</li> -->
     <li class="list-group-item" :class="{ willEdit: isActive }" :key="item.id" > {{index}}. {{item}}</li> 
     <i class="fas fa-check-circle"  @click="doneTask(index)"></i>     
     <i class="fas fa-times-circle"  @click="deleteTask(index)"></i>
     <button class="edit-task" @click="editTask(index)">Edit</button>
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
         arrayList: [],
         isActive: false,
         activeColor: 'red'
       }
     },
     methods : {
       sending : function (){
         this.arrayList.push(this.todo)
         this.todo = "";
     
        },
        doneTask : function (){
          this.activeColor = "greenyellow"
        },
        deleteTask : function (index){
        var confirm = window.confirm('Do you really want to erase your task?')
          if(confirm === true){
            // console.log('delete this', index);
            this.arrayList.splice(index, 1)
        } else{
          return;
          }

        },
        editTask: function (){
          this.isActive = true
          console.log(this.isActive)
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
