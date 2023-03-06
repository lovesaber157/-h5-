<template>
	<view id="app">
		<section class="content-header">
			<view id="h1">首页<small></small></view>
		</section>
		<section class="content">
			<view class="row">
				<view class="col-12">
					<img-swiper></img-swiper>
					<fr></fr>
					<fl></fl>
				</view>
			</view>
		</section>
	</view>
</template>

<script>
	import imgSwiper from "@/components/Home/imgSwiper/imgSwiper.vue"
	import fl from "@/components/Home/fl/fl.vue"
	import fr from "@/components/Home/fr/fr.vue"
	export default {
		name:"Home",
		components:{imgSwiper,fl,fr},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/scss/public.scss"
</style>