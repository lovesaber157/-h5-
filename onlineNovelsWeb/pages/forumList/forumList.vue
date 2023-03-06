<template>
	<mold>
		<forum-list :type="type"></forum-list>
	</mold>
</template>

<script>
	import mold from "@/components/mold/mold.vue"
	import forumList from "@/components/forumList/forumList.vue"
	export default {
		components:{mold,forumList},
		data() {
			return {
				type:Number
			};
		},
		onLoad(option) {
			this.type=Number(option.type)
		}
	}
</script>

<style lang="scss">

</style>
