<template>
	<view class="announcement-box card">
		<view class="card-head">
			公告
			<a>
				<span class="right-tag">查看更多>></span>
			</a>
		</view>
		<hr class="layui-bg-green">
		<view v-for="item in announcementList" @click="goToAnnInfo(item.annid)">
			<a>&nbsp;&nbsp;{{item.title}}</a>
			<span class="time">{{item.time}}</span>
			<hr class="layui-bg-gray">
		</view>
	</view>
</template>

<script>
	export default {
		name:"Announcement",
		data() {
			return {
				announcementList:{}
			};
		},
		methods:{
			goToAnnInfo(annid){
				uni.navigateTo({
					url:"/pages/annDetail/annDetail?annId="+annid
				})
			}
		},
		created() {
			let that=this
			uni.request({
				url:"/api/announcementList",
				method:'POST',
				success(res) {
					that.announcementList=res.data.slice(0,5)
				}
			})
		}
	}
</script>

<style lang="scss">
	@import "@/static/public.scss";
	.announcement-box{
		float: none;
	}
</style>