<template>
	<view class="content">
		<view>{{"hello"+msg}}</view>
		<image :src="src" mode="scaleToFill"></image>
		<view>
			<view class="items" 
				:class="{on:currentIndex===index}"
				v-for="(item,index) in movies" 
				:key="index"
				@click="itemClick(index)"
				>
				{{item}}
			</view>
		</view>
		
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	export default {
		data() {
			return {
				msg: '初次见面请多关照',
				src:"https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1578677698331&di=041ad356855c0687e927658d0e6c307f&imgtype=0&src=http%3A%2F%2Fn.sinaimg.cn%2Ffront%2F723%2Fw2048h1075%2F20190311%2F3rDy-htzuhtp6229276.jpg",
				movies:['飞驰人生','夏洛特烦恼','西虹市首富','羞羞的铁拳','海上钢琴师','绿皮书','荒野求生','阿甘正传','黑衣人','无敌破坏王'],
				currentIndex:0
			}
		},
		onLoad() {
				
		},
		onReady() {
			uni.startPullDownRefresh();
		},
		onPullDownRefresh() {
			console.log("开始执行")
			 this.getList();
		},
		onReachBottom(){
			console.log("加载中")
			const movies2 = ['美人鱼','冰雪奇缘','疯狂动物城','沉睡魔咒']
			this.movies.push(...movies2)
		},
		methods: {
			itemClick(i){
				this.currentIndex=i
			},
			getList(){
				setTimeout(()=>{
					console.log("执行完毕");
					uni.stopPullDownRefresh();
				},1500)
				
			},
			err(){
				console.log("错误")
			},
			end(){
				uni.stopPullDownRefresh()
			}
		},
		components:{
			test
		}
	}
</script>

<style>
	.items{
		height: 20px;
		font-size: 16px;
		line-height: 20px;
		text-align: center;
		padding: 15px 0px;
	}
	.on{
		color: #ff3636;
	}
</style>
