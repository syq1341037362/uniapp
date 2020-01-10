<template>
	<view>
		<text>{{stitle}}</text>
		<button class="t_btn"  size="default" @click="toParent">向父组件传值</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				msg:"我是子组件的值"
			};
		},
		props:{
			stitle:{
				type:String,
				default:"",
				required:true
			}
		},
		methods:{
			toParent(){
				uni.$emit('testEmit',this.msg)
			}
		}
	}
</script>

<style lang="scss" scoped>
	.t_btn{
		color: $uni-text-color-inverse;
		width: 180px;
		height: 30px;
		line-height: 30px;
		background-color: hotpink;
	}
</style>
