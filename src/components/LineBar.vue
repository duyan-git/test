<template>
	<div class="charts">
		<div id="myChart"></div>
	</div>
</template>

<script>
	import echarts from 'echarts'
	export default{
		// name:"chart",
		mounted() {
			let myChart=this.$echarts.init(document.getElementById('myChart'));
			myChart.setOption({
				tooltip:{},
				//右上角图例
				color:['#ff0000','#00aa00'], //图例颜色，与折线颜色一致
				legend:{
					show:true,
					//orient设置布局方式，默认horizontal水平布局，垂直布局vertical
					orient:'horizontal',
					X:'right',
					Y:'top',
					//图例与图表上下间距
					padding:10,
					right:1,
					//icon设置右上角图标样式
					data:[{name:'巡检时长',icon:'stack'},{name:'有效时长',icon:'stack'}],
					textstyle:{
						fontsize:6
					}
				},
				//图表距边框的距离，可用百分百/number
				grid:{
					top:'17%',
					left:'3%',
					right:'2%',
					containLabel:true
				},
				xAxis:{
					type:'category',
					data:['4H','8H','12H','14H','18H','22H','24H']
				},
				yAxis:{
					type:'value',
					//y轴最大值、最小值
					max:100,
					min:0
				},
				series:[
					{
						name:'巡检时长',
						type:'line',
						//设置拐点不显示
						symbol:'none',
						//设置曲线弧度，取0-1
						smooth:0.3,  
						itemStyle:{
							normal:{
								lineStyle:{
									color:'red',
									width:2
								}
							}
						},
						data:[60,50,35,36,45,80,65]
					},
					{
						name:'有效时长',
						type:'line',
						symbol:'none',
						//折线曲线弧度
						smooth:0.3,
						itemStyle:{
							normal:{
								lineStyle:{
									color:'green',
									width:2
								}
							}
						},
						data:[30,40,13,20,32,40,26]
					}
				]
			})
		}
	}
</script>

<style>
	#myChart{
		width: 350px;
		height:220px;
	}
</style>
