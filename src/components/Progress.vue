<template>
	<div class="prog">
		<div class="progressTitle" >{{progtitle}}</div>
		<div class="progressContainer">
			<div class="progressItem" :style="{width:barwidth*100+'%'}"></div>
		</div>
		<div class="prognum">{{num}}</div>	
		<div class="progpercent" v-show="percent<1">({{percent*100+'%'}})</div>
	</div>
</template>
<style>
	.prog{
		height:30px ;
		width: 520px;
		margin-left: 20px;
	}
	.progressContainer{
		position: relative;
		background-color: #aaa;
		height: 10px;
		width: 160px;
		border-radius: 5px;
		float: left;
		margin-top: 20px;
	}
	.progressItem{
		position: absolute;
		background-color: blue;
		height: 10px;
		width: 160px;
		border-radius: 5px;
		/* border: 1px solid blue; */
		
	}
	.progressTitle{
		float: left;
		margin-right: 5px;
		width: 100px;
		height: 10px;
		margin-top: 15px;
	}
	.prognum{
		float: left;
		margin-left: 5px;
		width: 10px;
		height: 10px;
		margin-top: 15px;
	}
	.progpercent{
		float: left;
		margin-left: 10px;
		width: 10px;
		height: 10px;
		margin-top: 15px;
	}
</style>
<script>
	export default{
		props:['progtitle','percent','num','barwidth']
	}
</script>
