<template>
	<mold>
		<novel-read :novelId="novelId"></novel-read>
	</mold>
</template>

<script>
	import novelRead from "@/components/novelRead/novelRead.vue"
	import mold from "@/components/mold/mold.vue"
	export default {
		components:{novelRead,mold},
		data() {
			return {
				novelId:""
			};
		},
		onLoad(option) {
			this.novelId=option.novelId
		}
	}
</script>

<style lang="scss">

</style>
