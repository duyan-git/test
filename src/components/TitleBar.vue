<template>
	<div>
		<div class="titleStyle"></div>
		<div style="float: left;margin-left: 5px;">{{conent}}</div>
	</div>
</template>

<script>
	export default{
		props:['conent']
	}
</script>

<style>
	.titleStyle{
		float: left;
		height: 15px;
		width: 3px;
		background-color: #0000FF;
		margin-top: 5px;
		margin-left: 15px;
	}
</style>
