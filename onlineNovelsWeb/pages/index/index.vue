<template>
	<mold :footerShow="true">
		<home></home>
	</mold>
</template>

<script>
	import mold from "@/components/mold/mold.vue"
	import Home from "@/components/Home/Home.vue"
	export default {
		components:{
			mold,Home
		},
		data() {
			return {
				
			}
		},
		onLoad() {
			getUserInfo:{
				uni.request({
					url:"/api/userInfo",
					method:"POST",
					success(res) {
						console.log(res.data)
					}
				})
			}
		},
	}
</script>

<style>
</style>
