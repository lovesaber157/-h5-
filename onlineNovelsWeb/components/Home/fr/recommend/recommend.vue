<template>
	<view class="recommend-box card">
		<view class="card-head">推荐</view>
		<hr class="layui-bg-green">
		<a>
			<view class="rec-title">&nbsp;&nbsp;三核怪书挖掘机</view>
			<view class="rec-brief">
				由于每天啃大量生肉，总觉得得记录一下看过什么，好看的和不好看的都会分享 评分-10到10之间，0是厕纸文，3是能看级别。
				有兴趣的可以来看看，只挖不埋，专业踩雷人。(因为把兴国也拖进来了，进化成了双核挖掘机(由于怜喵也要加入O趴，进化成三核了
			</view>
		</a>
		<hr class="layui-bg-gray">
		<a>
			<view class="rec-title">&nbsp;&nbsp;真白萌之里（X</view>
			<view class="rec-brief">
				还在为如何视奸审核，扫荡新书烦恼？<br />
				绝对不是杂志社•真白书目简评<br />
				专业跟踪狂团队，偷窥真白审核黑幕，为您带来第二时间的新书/新翻译/新作者简讯。<br />
				每期邀请最轻量级•真白嘉宾，让平时高冷无口的他们与大家亲密接触！<br />
			</view>
		</a>
		<hr class="layui-bg-gray">
		<a>
			<view class="rec-title">&nbsp;&nbsp;Online★Communication</view>
			<view class="rec-brief">
				一位少年因故变成了幼女的模样。这是发生在她身上的、关于友情与亲情的、温暖人心的日常故事。
			</view>
		</a>
		<hr class="layui-bg-gray">
		<a>
			<view class="rec-title">&nbsp;&nbsp;日本语探究丛书</view>
			<view class="rec-brief">
				这套丛书依次从语法、语音、词汇、文字、修辞、历史、方言等角度出发，以通俗易懂的语言为我们讲述了日本语学各个领域的基础知识，可作为了解日本语学的入门书籍。
			</view>
		</a>
		<hr class="layui-bg-gray">
		<a>
			<view class="rec-title">&nbsp;&nbsp;真白萌论坛使用指南</view>
			<view class="rec-brief">
				这个指南会随时更新，其中讲解了真白萌论坛的各种功能和使用方法。
				遇到问题时请先翻翻这个指南吧。<br>
				注意：请勿在本书任何章节水。 违者会被扣除金币和经验。管理员拥有最终解释权。
			</view>
		</a>
		<hr class="layui-bg-gray">
	</view>
</template>

<script>
	export default {
		name:"recommend",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@import "@/static/public.scss";
	.rec-title{
		font-weight: 600;
		font-size: 22rpx;
		text-align: left;
	}
	.rec-brief{
		font-size: 30rpx;
		text-align: left;
	}
</style>