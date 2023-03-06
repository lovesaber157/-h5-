<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">用户个人中心<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<center-head></center-head>
					<center-body></center-body>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import centerBody from "@/components/personalCenter/centerBody/centerBody.vue"
	import centerHead from "@/components/personalCenter/centerHead/centerHead.vue"
	export default {
		name:"personalCenter",
		components:{
			centerHead,centerBody
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss"
</style>