<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">首页<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<tab-list></tab-list>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import tabList from "@/components/leaderboard/tabList/tabList.vue"
	export default {
		name:"leaderboard",
		components:{
			tabList
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss";
</style>