<template>
	<view class="box">
		<div class="box-body">
			<div>
				<span class="cp-btn all-pull-down">全部收起</span>
				<span class="cp-btn cp-rank">倒序排列</span>
			</div>
		</div>
		<view class="chapter-content">
			<view class="chapter-ul">
				<li class="chapter-box">
					<span class="sign minus">-</span>
					<b>公告</b>
				</li>
				<li class="chapter-box">
					<span class="sign minus">-</span>
					<b>epub区</b>
				</li>
				<li>
					<ul class="episode-ul" style="height: 50px;">
						<a class="to-read">
							<li class="episode-box ">
								<span style="overflow: hidden; text-overflow: ellipsis; margin: 0px;">
									资源区(最后于5.18更新) 
								</span>
								<small style="font-size: 10px; transform: scale(0.8); color: red; text-align: right;">5G</small>
								<span style="font-size: 10px; text-align: right;">
									<span>22-01-12 15:44</span>
									<small style="font-size: 85%;">(<u>更新</u>)</small>
								</span>
							</li>
						</a>
					</ul>
				</li>
			</view>
		</view>
		<view style="clear: both;"></view>
	</view>
</template>

<script>
	export default {
		name:"nvChapters",
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
	.box{
		background-color: white;
		position: relative;
		border-radius: 3px;
		border-top: 0px solid #d2d6de;
		margin-bottom: 20px;
		width: 80%;
		margin: auto;
		overflow: hidden;
		@media screen and (max-width: 960px){
			&:first-of-type{
				padding: 0px;
			}
			margin-bottom: 0px;
			border: none;
			position: relative;
			border-radius: 3px;
			background-color: #ffffff;
			border-top: 0px solid #d2d6de;
			width: 100%;
			margin: auto;
		}
	}
	.box-body{
		border-top-left-radius: 0;
	    border-top-right-radius: 0;
	    border-bottom-right-radius: 3px;
	    border-bottom-left-radius: 3px;
	    padding: 10px;
		.cp-btn{
			width: 80px;
		    float: right;
		    background-color: #274988;
		    color: white;
		    text-align: center;
		    line-height: 25px;
		    border-radius: 5px;
		    font-size: 10px;
		    cursor: pointer;
		    display: block;
		    margin: 10px;
		}
	}
	ul {
		margin: 0;
	    margin-bottom: 10px;
		li {
		    list-style: none;
		}
		ul{
			margin-bottom: 0;
		}
	}
	.chapter-ul{
		display: block;    
		width: 100%;
		padding: 0px;
		list-style: none;
		.chapter-box{
			display: block;
		    width: 100%;
		    height: 50px;
		    line-height: 50px;
		    text-align: center;
		    overflow: hidden;
		    text-overflow: ellipsis;
		    white-space: nowrap;
		    cursor: pointer;
		}
	}	
	.to-read{
		text-decoration: none;
	}
	.episode-ul{
		height: 50px;
		padding: 0px;
		overflow: hidden;
		transition: height .6s;
		.episode-box{
			padding: 0 5%;
			display: grid;
			grid-template-columns: 18fr 1fr 1fr;
			// width: 100%;
			height: 50px;
		    line-height: 50px;
		    text-align: left;
		    overflow-wrap: break-word;
			overflow: hidden;
			text-overflow: ellipsis;
			white-space: nowrap;
			span{
				text-decoration: none;
				transition: all .14s linear;
				text-shadow: 1px 1px 1px #fff;
				transform: translateZ(0) scale(1,1);
				color: black;
				margin-left: 20px;
				small{
					font-size: 85%;
				}
			}
		}
	}
</style>