<template>
	<swiper class="swiper" autoplay circular>
		<swiper-item class="item">
			<image src="/api/image/Home1.jpg"></image>
		</swiper-item>
		<swiper-item class="item">
			<image src="/api/image/Home2.jpg"></image>
		</swiper-item>
		<swiper-item class="item">
			<image src="/api/image/Home3.jpg"></image>
		</swiper-item>
	</swiper>	
</template>

<script>
	export default {
		name:"imgSwiper",
	}
</script>

<style lang="scss">
	.swiper{
		width: 100%;
		height: 200px;
	    position: relative;
	    left: 0;
	    top: 0;
	    background-color: #f8f8f8;
		image{
			width: 100%;
			height: 100%;
		}
	}
</style>