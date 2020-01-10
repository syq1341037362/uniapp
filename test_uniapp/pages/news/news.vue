<template>
	<view>
		
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	export default {
		data() {
			return {
				
			};
		},
		onLoad() {
			console.log("页面初始化执行一次 onLoad")
		},
		onReady() {
			console.log("页面加载完毕 执行一次 onReady")
		},
		onHide() {
			console.log("页面离开执行 执行多次 onHide")
		},
		onShow() {
			console.log("页面进入执行 执行多次 onShow")
		},
		components:{
			test
		}
	}
</script>

<style lang="scss">

</style>
