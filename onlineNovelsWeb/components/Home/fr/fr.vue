<template>
	<view class="fr">
		<Announcement></Announcement>
		<recommend></recommend>
		<mycollection></mycollection>
	</view>
</template>

<script>
	import Announcement from "@/components/Home/fr/Announcement/Announcement.vue"
	import recommend from "@/components/Home/fr/recommend/recommend.vue"
	import mycollection from "@/components/Home/fr/mycollection/mycollection.vue"
	export default {
		name:"fr",
		components:{Announcement,recommend,mycollection},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.fr{
		@media screen and (max-width:960px){
			float: left;
			width: 100%;
		}
		float: left;
		width: 49%;
	}
</style>