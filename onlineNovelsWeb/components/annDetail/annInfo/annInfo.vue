<template>
	<view class="card">
		<view class="card-head">{{announcement.title}}</view>
		<view class="author">
			{{announcement.author}}<text class="time">{{announcement.time}}</text>
		</view>
		<view class="card-body">
			<br>
			<view class="h4">
				<br>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"annInfo",
		props:{
			annId:Number
		},
		data() {
			return {
				announcement:{},
				h4:{}
			};
		},
		created(){
			let that=this
			uni.request({
				url:"/api/announcementList/detail",
				method:"POST",
				data:{
					annId:this.annId
				},
				success(res) {
					that.announcement=res.data
					document.getElementsByClassName("h4")[0].innerHTML=that.announcement.innerText
				}
			})
		},
	}
</script>

<style lang="scss">
	.card{
		width: 100%;
		position: relative;
		margin-left: 0;
		margin-right: 0;
		height: auto;
		display: block;
		border: 1px solid #eee;
		border-radius: 6px;
		margin-top: 20px;
		position: relative;
		transition: all 0.2s ease-in-out;
		background: white;
		min-height: 500px;
		padding: 10px;
	}
	.card-head{
		width: 100%;
		padding: 10px;
		// height: 30px;
		height: auto;
		font-size: 17px;
		text-align: center;
		font-weight: 600;
		color: gray;
		line-height: 30px;
	}
	.author{
		width: 100%;
		padding: 5px;
		height: 20px;
		font-size: 10px;
		color: gray;
		text-align: center;
		line-height: 20px;
		.time{
			font-size: 10px;
			transform: scale(0.8);
			line-height: 25px;
			margin-left: 10px;
		}
	}
	.card-body{
	    padding: 10px;
	    text-indent: 10px;
	}
	.h4{
		font-size: 18px;
		margin:10px 0;
		font-weight: 500;
		line-height: 1.1;
	}
	p{
		margin: 0 0 10px;
	}
</style>