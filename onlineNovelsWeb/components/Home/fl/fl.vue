<template>
	<view class="fl">
		<new-up></new-up>
		<random></random>
	</view>
</template>

<script>
	import newUp from "@/components/Home/fl/newUp/newUp.vue"
	import random from "@/components/Home/fl/random/random.vue"
	export default {
		name:"fl",
		components:{newUp,random},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.fl{
		@media screen and (max-width:960px){
			float: left;
			width: 100%;
		}
		float: right;
		width: 49%;
	}
</style>