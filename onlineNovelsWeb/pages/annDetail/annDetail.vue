<template>
	<mold>
		<ann-detail :annId="annId"></ann-detail>
	</mold>
</template>

<script>
	import annDetail from "@/components/annDetail/annDetail.vue"
	import mold from "@/components/mold/mold.vue"
	export default {
		components:{mold,annDetail},
		data() {
			return {
				annId:-1
			};
		},
		onLoad(option) {
			this.annId=Number(option.annId)
		}
	}
</script>

<style lang="scss">

</style>
