<template>
	<div class="emp">
		<div class="buttonbar">
			<button-bar></button-bar>
		</div>
		</br>
		<div class="progressbar">
		  <TitleBar conent="巡检总人数"></TitleBar>
		  <div style="float: left;" v-for="(item,index) in list">
		  	<ProgressBar 
		  	:progtitle="item.name" 
		  	:num="item.num" 
		  	:percent="item.percent" 
		  	:key="item.index" 
		  	:barwidth="item.percent">
		  	</ProgressBar>
		  </div>
		</div>
		<div class="linebar">
			<TitleBar conent="巡检时长每日走势"></TitleBar>
			<LineBar></LineBar>
		</div>
	</div>
</template>
<script>
	import TitleBar from '../components/TitleBar.vue'
	import ProgressBar from '../components/Progress.vue'
	import LineBar from '../components/LineBar.vue'
	import ButtonBar from '../components/ButtonBar.vue'
	import Msg from '../components/msg.js'
	export default{
		components:{
			TitleBar,
			ProgressBar,
			LineBar,
			ButtonBar
		},
		data(){
			var _this=this;
			var list=[];
			this.$http.get("json/emplist.json").then(function(res){
				 _this.list=res.data;
			})
			return{
				list:[],
				kk:0
			}
		},
		mounted() {
			var _this=this
			Msg.$on('val',function(m){
				_this.kk=m
			})
		}
			
		}
</script>

<style>
	.progressbar{
		
		/* margin-top: 30px; */
		align-items: center;
		/* border: 1px solid #000; */
		width: 350px;
		height: 150px;
		
	}
	.{
		margin-left: 20px;
	}
	/* .emp{
		width: 350px;
		height: 150px;
		background-color: #42B983;
		margin: 0 auto;
		margin-top: 25px;
	} */
	.linebar{
		float: left;
		/* margin-top: 20px; */
	}
	.buttonbar{
		display: flex;
		/* border: 1px solid #000; */
		/* width: 300px;
		height: 50px; */
		margin-top: 30px;
		align-items: center;
	}
</style>
