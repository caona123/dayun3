<template>

  <div class="hello">
    {{message}}
    <span v-text="info"></span>
    <input type="text" name=""v-model="message">


    <hr>
    <ul>
      <li v-for="(v,index) in lists">{{index}}---{{v.id}}---{{v.title}}</li>

    </ul>

    <button v-on:click="go()">点击</button>
    <button @click="run()">击重</button>



  </div>
</template>

<script>
export default {
     name:"hello",
      data(){
        return{
          message:'hello world',
          info:'我是Vue',
          lists:[
            {id:1,title:'去吃饭'},
            {id:2,title:'打篮球'},
            {id:3,title:'睡觉'},
            {id:4,title:'打豆豆'},
            {id:5,title:'敲代码'},
          ]
        }

    	},
    		methods:{
    			go(){
    				console.log('go go go')
    			}
    			,
    			run(){
    				console.log("run run run")
    			}
    		}

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.done{
			color:green;
			text-decoration: line-through;
		}
</style>
