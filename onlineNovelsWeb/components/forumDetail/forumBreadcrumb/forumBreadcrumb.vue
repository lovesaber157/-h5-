<template>
	<view class="breadcrumb">
		<view>香格里拉</view>
		<span>></span>
		<view>论坛</view>
	</view>
						
</template>

<script>
	export default {
		name:"forumBreadcrumb",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.breadcrumb{
		visibility: visible;
		font-size: 0;
		view{
			color: #999;
			display: inline;
		}
		>*{
			font-size: 14px;
		}
		span{
			margin:0 10px;
			color: #999;
		}
	}
</style>