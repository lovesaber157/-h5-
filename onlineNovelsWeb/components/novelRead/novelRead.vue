<template>
	<view id="app" :novelId="novelId">
		<section class="content-header">
			<view id="h1">小说名称<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<nv-info-box></nv-info-box>
				</view>
			</view>
			<view class="row">
				<view class="col-12">
					<nv-chapters></nv-chapters>
				</view>
			</view>
			<view class="row">
				<view class="col-12">
					<nv-comment></nv-comment>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import nvInfoBox from "@/components/novelRead/nvInfoBox/nvInfoBox.vue"
	import nvChapters from "@/components/novelRead/nvChapters/nvChapters.vue"
	import nvComment from "@/components/novelRead/nvComment/nvComment.vue"
	export default {
		name:"novelRead",
		props:{
			novelId:String
		},
		components:{nvInfoBox,nvChapters,nvComment},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss"
</style>