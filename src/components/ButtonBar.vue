<template>
	<div class="btt">
		<ul class="buttonBar">
			<li v-for="(item,index) in nav" @click="selectNav(item.name,index)">
				<img :src="isSelect==index?item.url_one:item.url" alt="item.name"/>
				<p :class="isSelect==index?'active':''">{{item.name}}</p>
			</li>
		</ul>
	</div>
</template>
<style>
	.buttonBar p{
		font-size: 10px;
		line-height: 1px;
	}
	.buttonBar li{
		float: left;
		list-style-type: none;
		display: inline;
		text-align: center;
		margin-left: 10px;
		/* padding-bottom: 2px; */
		vertical-align: middle;
		/* margin-top: 30px; */
		
	}
	.buttonBar img{
		height: 38px;
		width: 38px;
	}
	.active{
		color: red;
	}
</style>
<script>
	import Msg from './msg.js'
	export default{
		data(){
			return{
				isSelect:0,
				nav:[
					{name:"巡检",url:require("../../public/img/XunJian/XunJian.png"),url_one:require('../../public/img/XunJian/XunJianActive.png')},
					{name:"安检",url:require("../../public/img/XunJian/AnJian.png"),url_one:require('../../public/img/XunJian/AnJian.png')},
					{name:"抢修",url:require("../../public/img/XunJian/QiangXiu.png"),url_one:require('../../public/img/XunJian/QiangXiuActive.png')},
					{name:"隐患",url:require("../../public/img/XunJian/YinHuan.png"),url_one:require('../../public/img/XunJian/YinHuan.png')},
					{name:"工地",url:require("../../public/img/XunJian/GongDi.png"),url_one:require('../../public/img/XunJian/GongDi.png')},
					{name:"设备",url:require("../../public/img/XunJian/SheBei.png"),url_one:require('../../public/img/XunJian/SheBei.png')},
				]
			}
		},
		methods:{
			
			selectNav(name,ins){
				this.isSelect=ins,
				Msg.$emit('val',ins)
				// console.log(ins)
			}
		}
	}
</script>


