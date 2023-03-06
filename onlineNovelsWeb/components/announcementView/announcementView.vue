<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">公告<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<ann-list></ann-list>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import annList from "@/components/announcementView/annList/annList.vue"
	export default {
		name:"announcementView",
		components:{annList},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss"
</style>