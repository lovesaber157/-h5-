<template>
	<view :class="wrapperClassName">
		<main-header :changeClassName="changeClassName"></main-header>
		<main-side-bar></main-side-bar>
		<view class="content-wrapper">
			<!--插入模板-->
			<slot></slot>
		</view>
		<mainFooter v-if="footerShow"></mainFooter>
	</view>
</template>

<script>
	import mainHeader from "@/components/mainHeader/mainHeader.vue"
	import mainSideBar from "@/components/mainSideBar/mainSideBar.vue"
	import mainFooter from "@/components/mainFooter/mainFooter.vue"
	export default {
		name:"mold",
		props:{
			footerShow:Boolean
		},
		components:{
			mainHeader,mainSideBar
		},
		data() {
			return {
				wrapperClassName:"wrapper sidebar-collapse"
			};
		},
		methods:{
			changeClassName(){
				//正常版本 min-width:767px
				//sidebar-collapse控制正常版本是否打开
				//缩小屏幕
				//sidebar-open控制小屏幕是否打开
				if(window.matchMedia("(min-width:767px)").matches){
					if(this.wrapperClassName.includes("sidebar-collapse")){
						let a=[]
						for(let i of this.wrapperClassName.split(" ")){
							if(i!=="sidebar-collapse")
								a.push(i)
						}
						this.wrapperClassName=a.join(" ")
					}else{
						this.wrapperClassName+=" sidebar-collapse"
					}
				}else{
					if(this.wrapperClassName.includes("sidebar-open")){
						let a=[]
						for(let i of this.wrapperClassName.split(" ")){
							if(i!=="sidebar-open")
								a.push(i)
						}
						this.wrapperClassName=a.join(" ")
					}else{
						this.wrapperClassName+=" sidebar-open"
					}
				}
			}
		}
	}
</script>

<style lang="scss">
	@media (max-width:767px) {
		.content-wrapper{
			margin-left: 0 !important;
		}
	}
	.wrapper{
		min-height: 100%;
		position: relative;
		overflow: hidden;
		// background-color: #f9fafc;
		.content-wrapper{
			border-left: 1px solid #d2d6de;
			min-height: 100%;
			background-color: #ecf0f5;
			transition: transform .3s ease-in-out,margin .3s ease-in-out;
			margin-left: 230px;
		}
	}
	.sidebar-open{
		.content-wrapper{
			@media (max-width:767px) {
				transform: translate(230px,0);
			}
		}
	}
	.wrapper.sidebar-collapse{
		@media (min-width:768px) {
			.content-wrapper{
				margin-left: 50px;
			}
		}
	}
	.wrapper.sidebar-open{
		.main-sidebar{
			transform: translate(0,0) !important;
		}
	}
</style>