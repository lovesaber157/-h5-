<template>
	<view class="new-update-box card">
		<view class="card-head">
			随机推荐
			<view class="right-tag">
				<i class="iconfont icon-shuaxin"></i>
				刷新
			</view>
		</view>
		<hr class="layui-bg-green">
		<view class="update-cards">
			<view v-for="(item,index) in storyInfo">
				<a>
					<view class="card-item">
						<view class="card-image-box">
							<image :src="'/api/image/'+item.imageName" class="card-image"></image>
						</view>
						<view class="card-info">
							<view class="update-store-title">
								{{item.storeTitle}}
							</view>
							<view class="update-store-chapter">
								{{item.upDateChapter}} 
							</view>
						</view>
					</view>
				</a>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:"random",
		data() {
			return {
				storyInfo:[
					{
						storeTitle:"我在星際國家當惡德領主",
						upDateChapter:"WEB 第六章 88. 序章 ",
						imageName:"storeimg04.jpg",
						upDateTime:"16:04:20"
					},
					{
						storeTitle:"Nostalgia world online",
						upDateChapter:"web第七章 第七章 第七話 去大空洞探險吧 ⑥",
						imageName:"storeimg10.jpeg",
						upDaterTime:"08:00:03"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageName:"storeimg05.jpg",
						upDaterTime:"08:00:03"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageName:"storeimg05.jpg",
						upDaterTime:"08:00:03"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageName:"storeimg05.jpg",
						upDaterTime:"08:00:03"
					},
					{
						storeTitle:"转生成小小妖精",
						upDateChapter:"web 第三章 魔物狂潮 072 藥水",
						imageName:"storeimg05.jpg",
						upDaterTime:"08:00:03"
					},
				]
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/public.scss";
	.icon-shuaxin{
		margin-right: 6rpx;
	}
</style>