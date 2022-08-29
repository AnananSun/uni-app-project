<template>
	<!-- web标签无法转化成小程序可解析的标签 -->
	<!-- 必须使用官方提供的 兼容性标签  view text....等开发才能使用app 小程序 -->
	<!-- 	<div>
		<h1>Hello world</h1>
	</div> -->
	<view class="">
		<text>Hello World</text>
		<navigator url="/pages/detail/detail">点我去详情页</navigator>
		<!-- alt + / 可以弹出提示 -->
		<button type="default" size="mini" @click="goDetail()">详情页</button>
	</view>
</template>

<script>
export default {
	data() {
		return {
			name:"安洪波",
			age:25
		}
	},
	methods: {
		goDetail(){
			// 跳转页面的api
			uni.navigateTo({
				// 目标地址,用模板字符串进行传值
				url:`/pages/detail/detail?name=${this.name}&age=${this.age}`,
				
				success: () => {},
				fail: () => {},
				complete: () => {}
			})
		}
	}
}
</script>

<style scoped></style>
