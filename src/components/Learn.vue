<template lang="html">
  <div class="learn">

    <button @click="ifIsShow=!ifIsShow" class="btn btn-success">if显示/隐藏{{ifIsShow}}</button>
     <div class="box" v-if="ifIsShow">
     	我是切换的div  if
     </div>
     <br>
     <button @click="showIsShow=!showIsShow" class="btn btn-success">show显示/隐藏{{showIsShow}}</button>
 	<div class="box" v-show="showIsShow">
     	我是切换的div  show
     </div>

  </div>
</template>

<script>
export default {
  name:"learn",
  data(){
    return{
      ifIsShow:true,
      showIsShow:true
    }

 }

}
</script>

<style lang="css">
.box{
			width: 300px;
			height: 300px;
			background: pink;
      margin:0 auto;
		}
</style>
