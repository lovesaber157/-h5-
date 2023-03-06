<template>
	<view>
		<view id="app">
			<section class="content-header">
				<view id="h1">公告详情<small></small></view>
			</section>
			<section class="content">
				<view class="row">
					<view class="col-12">
						<ann-info :annId="annId"></ann-info>
					</view>
				</view>
			</section>
		</view>
	</view>
</template>

<script>
	import annInfo from "@/components/annDetail/annInfo/annInfo.vue"
	export default {
		name:"annDetail",
		components:{annInfo},
		props:{
			annId:Number
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