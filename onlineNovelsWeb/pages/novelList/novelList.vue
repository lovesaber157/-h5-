<template>
	<mold>
		<novelList :classify="classify"></novelList>
	</mold>
</template>

<script>
	import novelList from "@/components/novelList/novelList.vue"
	import mold from "@/components/mold/mold.vue"
	export default {
		props:{mold,novelList},
		data() {
			return {
				classify:""
			};
		},
		onLoad(option) {
			this.classify=option.classify
			console.log(option.classify)
		}
	}
</script>

<style lang="scss">

</style>
