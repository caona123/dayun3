<template lang="html">
  <div class="third">
    <div class="panel panel-default">
     <div class="panel-heading">
        <h3 class="panel-title">Tolist ({{total}})</h3>
     </div>
     <div class="panel-body">

        <ul class="list-group">
            <li :class="{done:item.completed}" v-for="(item,index) in todos"　class="list-group-item">{{item.title}}
            {{item.completed}}
      <button :class="item.completed?'btn-danger':'btn-success'"  class="btn btn-success pull-right btn-sm	" @click="toggleState(index)">

       {{item.completed?'已完成':'完成'}}
      </button>
      <button class="btn btn-info btn-sm pull-right" @click="deleteItem(index)">删除</button>
            </li>

        </ul>

        <input type="text" name="" class="form-control" v-model="newData.title">
        <button  @click="addNews(newData)" class="btn  btn-success">添加</button>
     </div>
     <div class="panel-footer">

     </div>
 </div>



  </div>
</template>

<script>
export default {
    name:"third",
    data(){
      return{
        newData:{
         id:null,
         title:'',
         completed:false
       },

       todos:[
         {
           id:1,
           title:'去吃饭',
           completed:false
         },
         {
           id:2,
           title:'去睡觉',
           completed:false
         },
         {
           id:3,
           title:'打豆豆',
           completed:false
         },
         {
           id:4,
           title:'张喜龙',
           completed:false
         },
         {
           id:5,
           title:'张喜龙',
           completed:false
         }

       ]
      }



  }
  ,
 methods:{
   addNews(data){
     this.todos.push(data);
     this.newData ={
       id:null,
       title:'',
       completed:false
     };

   },
   toggleState(index){
     this.todos[index].completed = !this.todos[index].completed;
     console.log(index)
   },

     deleteItem(index){
       this.todos.splice(index,1)
     }

 },
 computed:{
   total(){
     return this.todos.length
   }
 }
}
</script>

<style lang="css">
.done{
    color:green;
    text-decoration: line-through;
  }
</style>
