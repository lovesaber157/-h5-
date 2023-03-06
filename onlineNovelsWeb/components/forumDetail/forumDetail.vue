<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">香格里拉<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<forum-breadcrumb></forum-breadcrumb>
					<forum-head></forum-head>
					<forum-body></forum-body>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import forumBreadcrumb from "@/components/forumDetail/forumBreadcrumb/forumBreadcrumb.vue"
	import forumHead from "@/components/forumDetail/forumHead/forumHead.vue"
	import forumBody from "@/components/forumDetail/forumBody/forumBody.vue"
	export default {
		name:"forumDetail",
		components:{
			forumBreadcrumb,forumHead,forumBody
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