<template>
	<view class="box n-h">
		<view class="bg"></view>
		<view class="box-body z-index">
			<view class="novel-title">我怎么可能成为你的恋人，不行不行！（※不是不可能！？）</view>
			<view class="with-border">
				<span>
					<view class="mailbox-attachment-icon has-img">
						<a>
							<image class="img img-thumbnail" mode="widthFix"  src="@/static/photos/linmeng.jpg"></image>
						</a>
					</view>
				</span>
			</view>
			<view class="n-detail">
				<view class="author">作者 : 
					<a>みかみてれん</a>
				</view> 
				<view class="n-translator">翻译 :
					<a>
					白鸠ちゃん
					</a>
					&nbsp;
				</view> 
				<view class="n-status">状态 :连载中</view> 
				<view class="tags">
					<span style="display: block;">
					标签 :
						<a>
							<span class="label label-success">恋爱喜剧</span>
						</a> 
						<a>
							<span class="label label-success">百合</span>
						</a> 
						<a>
							<span class="label label-success">女性主角</span>
						</a> 
						<a>
							<span class="label label-success">校园</span>
						</a>
						<a>
							<span class="label label-success">青梅竹马</span>
						</a> 
						<a>
							<span class="label label-success">欢乐向</span>
						</a>
					</span>
				</view>
				<view class="n-update">
					更新 : 
					<a class="nw-a">第五卷 制作信息 </a> 
					<span class="s-font">2023-02-24 18:48:49</span>
				</view>
				<view class="n-hot">
				热度 : 892评论 8811点赞 4018收藏 6838阅读
				</view> 
				<view class="n-chapters">字数 : 295592字共35话</view>
				<view class="n-ori">原作 : わたしが恋人になれるわけないじゃん、ムリムリ！（※ムリじゃなかった!）</view>
			</view>
			<view class="btn-box">
				<span class="n-btn btn-forum btn-font ">论&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;坛</span>
				<span class="n-btn btn-collect btn-font">收&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;藏</span> 
				<span class="n-btn btn-uncollect btn-font" style="display: none;">已收藏</span>
				<span class="n-btn btn-share btn-font ">分&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;享</span>
				<span class="n-btn btn-read btn-font reading">继续阅读</span>
			</view>
			<view style="clear: both;"></view>
		</view>
		<view class="box-footer z-index">
			<view class="brief">简介：第五卷</view>
			<view style="clear: both;"/>
		</view>
		<view style="clear: both;"></view>
	</view>
</template>

<script>
	export default {
		name:"nvInfoBox",
		props:["novelDetail"],
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	@media screen and (max-width: 960px){
		.box:forst-of-type{
			padding: 0;
		}
		.box{
			border: none !important;
			width: 100% !important;
		}
		.n-h {
		    border-radius: 0px !important;
		    height: 500px;
		}
	}
	.box{
		position: relative;
		border-radius: 3px;
		border-top: 0px solid #d2d6de;
		margin-bottom: 20px;
		width: 80%;
		margin: auto;
		overflow: hidden;
	}
	.bg{
		background-image: url("@/static/photos/storeimg03.jpg");
		background-repeat: no-repeat;
	    background-position: inherit;
	    background-size: cover;
	    position: absolute;
	    filter: brightness(0.5);
		top: -30px;
	    bottom: -30px;
	    left: -30px;
	    right: -30px;
		background-color: white;
	}
	.z-index{
		z-index: 1;
		position: relative;
	}
	.box-body{
		border-top-left-radius: 0;
		border-top-right-radius: 0;
		border-bottom-right-radius: 3px;
		border-bottom-left-radius: 3px;
		padding: 10px;
	}
	.tags, .n-update, .novel-title, .n-hot {
	    display: -webkit-box;
	    -webkit-line-clamp: 2;
	    -webkit-box-orient: vertical;
	    overflow: hidden;
	}
	.novel-title{
		font-weight: bold;
		text-align: center;
		width: 100%;
		font-size: 16px;
	}
	.n-h{
		border-radius: 20px 20px 0px 0px !important;
		color: #ffffff;
		min-height: 450px;
		font-weight: 800;
		a{
			color: white;
		}
	}
	.with-border{
		float: left;
		width: 30%;
		height: 180px;
		margin-top: 10px;
		padding-left: 10px;
	}
	.mailbox-attachment-icon.has-img{
		padding: 0;
	}
	.mailbox-attachment-icon {
	    text-align: center;
	    font-size: 65px;
	    color: #666;
	    padding: 20px 10px;
	}
	.img-thumbnail{
		width: 120px;
		display: inline-block;
		max-width: 100%;
		height: auto;
		padding: 4px;
		line-height: 1.42857143;
		background-color: #fff;
		border: 1px solid #ddd;
		border-radius: 4px;
		transition: all .2s ease-in-out;
	}
	image{
		vertical-align: middle;
	}
	.n-detail{
		@media screen and(max-width:960px){
			margin-left:  10px;
		}
		float: left;
	    width: 45%;
	    height: 200px;
	    margin-top: 10px;
	    text-align: left;
	    font-size: 10px;
		.author, .n-translator, .n-chapters {
		    display: -webkit-box;
		    -webkit-line-clamp: 1;
		    -webkit-box-orient: vertical;
		    overflow: hidden;
		}
		.n-translator, .n-status, .tags, .n-update, .n-hot, .n-chapters, .n-ori {
		    margin-top: 5px;
		}
		.author {
		    width: 100%;
		    /* margin-top: 5px; */
		}
		.n-ori{
			display: -webkit-box;
			-webkit-box-orient: vertical;
			overflow: hidden;
		}
	}
	a{
		text-decoration: none;
	}
	.label-success{
		background-color: #00a65a;
		color: #fff
	}
	.label{
		margin: 0;
		display: inline;
	    padding: .2em .6em .3em;
		margin-left: 5px;
	    font-size: 75%;
	    font-weight: 700;
	    line-height: 1;
		text-align: center;
	    white-space: nowrap;
	    vertical-align: baseline;
	    border-radius: .25em;
	}
	.tags, .n-update, .novel-title, .n-hot {
	    display: -webkit-box;
	    -webkit-line-clamp: 2;
	    -webkit-box-orient: vertical;
	    overflow: hidden;
	}
	.s-font{
		font-size: 10px;
	    transform: scale(0.8);
	}
	.btn-box{
		display: block;
		float: left;
		width: 20%;
		height: 180px;
		margin-top: 10px;
		.n-btn{
			text-align: center;
			background-color: #add8e645;
			line-height: 25px;
			border-radius: 5px;
			font-size: 10px;
			cursor: pointer;
			display: block;
			margin: 10px;
		}
	}
	.box-footer{
	    display: flex;
	    justify-content: space-evenly;
	    align-items: center;
	    background: none;
	    border-top: 0.5px solid #939393;
	}
	.brief{
		@media screen and (max-width: 960px){
			padding: 0;
			font-size: 11px;
		}
		display: inline-block;
		width: 100%;
		padding: 0 8%;
		margin: auto;
		text-align: left;
		font-size: 12px;
	}
</style>