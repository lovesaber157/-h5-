<template>
	<view id="app" :classify="classify">
		<section class="content-header">
			<view id="h1">全部小说<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<nv-head></nv-head>
					<nv-display :classify="classify"></nv-display>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import nvHead from "@/components/novelList/nvHead/nvHead.vue"
	import nvDisplay from "@/components/novelList/nvDisplay/nvDisplay.vue"
	export default {
		name:"novelList",
		components:{nvHead,nvDisplay},
		props:{classify:String},
		data() {
			return {
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss"
</style>