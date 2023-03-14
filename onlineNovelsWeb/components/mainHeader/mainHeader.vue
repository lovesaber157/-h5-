<template>
	<view class="main-header">
		<a class="logo">
			<span class="logo-mini">
				<image src="@/static/photos/sora.jpg"></image>
			</span>
			<span class="logo-lg">
				<text class="b">Masiro</text>
			</span>
		</a>
		<nav class="navbar navbar-static-top">
			<span class="sidebar-toggle" @click="changeClassName">
				<text class="iconfont icon-caidanlan"></text>
				<text class="sr-only">Toggle navigation</text>
			</span>
			<ul class="nav navbar-nav" style="float: left;"></ul>
			<view class="navbar-custom-menu">
				<ul class="nav navbar-nav">
					<li>
						<view id="message" class=" message-bell" style="float:left;margin-right:5px;">
							<span class="message-bell-btn">
								<text class="iconfont icon-lingdang"></text>
								<span class="badge-dot"></span>
							</span>
							<span class="message-bell-btn">
								<text class="iconfont icon-fuhao-"></text>
								
							</span>
						</view>
					</li>
					<li :class="userMenuClassName" @click="toShowDMenu()">
						<a class="dropdown-toggle">
							<image src="@/static/photos/other-220315104645-DNdv.jpg" class="user-image"></image>
							<text class="hidden-xs">NPC001</text>
						</a>
						<dropdown-menu></dropdown-menu>
					</li>
				</ul>
			</view>
		</nav>
	</view>
</template>

<script>
	import dropdownMenu from "@/components/mainHeader/dropdownMenu/dropdownMenu.vue"
	export default {
		name:"mainHeader",
		props:{
			changeClassName:Function
		},
		components:{
			dropdownMenu
		},
		data() {
			return {
				isShow:false,
				userMenuClassName:"dropdown user user-menu"
			};
		},
		methods:{
			toShowDMenu(){
				if(this.userMenuClassName==="dropdown user user-menu open"){
					this.userMenuClassName="dropdown user user-menu"
				}else{
					this.userMenuClassName="dropdown user user-menu open"
				}
			}
		}
	}
</script>

<style lang="scss">
	.navbar-nav{
		padding: 7.5px -15px;
	}
	.nav{
		padding-left: 0;
		list-style: none;
	}
	.message-bell{
		color: #000;
		margin: 10px 20px;
		display: inline-block;
	}
	@media (max-width:767px) {
		.main-header{
			.logo,.navbar{
				width: 100%;
				float: none;
			}
			.navbar{
				margin: 0;
			}
			.navbar-custom-menu{
				float: right;
			}
		}
		.hidden-xs{
			display: none;
		}
		.navbar-nav>.user-menu .user-image {
		    float: none;
		    margin-right: 0;
		    margin-top: -8px;
		    line-height: 10px;
		}
	}
	.nav{
		li{
			float: left;
		}
	}
	@media (min-width:768px) {
		.navbar{
			>.li{
				float: left;
			}
		}
	}
	@media screen and (max-width:960px){
		.main-header{
			.logo{
				display: none;
			}
		}
	}
	@media (max-width:991px) {
		.navbar-custom-menu{
			>.navbar-nav{
				float: right;
				>li{
					position: static;
					float: left;
				}
			}
			.navbar-nav{
				margin: 0;
				li>a{
					padding-top: 15px;
					padding-bottom: 15px;
					line-height: 20px;
				}
				li>.dropdown-menu{
					position: absolute;
					right: 5%;
					left: auto;
					border: 1px solid #ddd;
					background: #fff;
				}
			}
		}
	}
	.main-header{
		position: relative;
		max-height: 100px;
		z-index: 300;
		.navbar{
			position: relative;
			transition: margin-left .3s ease-in-out;
			margin-bottom: 0;
			//
			// margin-left: 230px;
			//
			border: none;
			margin-bottom: 20px;
			min-height: 50px;
			border-radius: 0;
			background: linear-gradient(45deg,#60eda0,#6febff, #9198e5);
			.sidebar-toggle{
				color: #f6f6f6;
				background: rgba(0, 0, 0, 0.1);
			}
			.nav>li>a{
				padding-bottom: 40rpx;
			}
		}
		.sidebar-toggle{
			float: left;
			padding: 14px 15px;
			&:hover{
				background-color: #60eda0;
			}
			.sr-only{
				position: absolute;
				width: 1px;
				height: 1px;
				margin: -1px;
				overflow: hidden;
				clip: rect(0,0,0,0);
			}
		}
		.logo{
			overflow: hidden;
			font-weight: 300;
			padding: 0 15px;
			width: 230px;
			float: left;
			height: 50px;
			font-size: 20px;
			line-height: 50px;
			text-align: center;
			color: #fff;
			background: linear-gradient(45deg,#9198e5,#6febff, #60eda0) !important;
			transition: width .3s ease-in-out;
			.logo-mini{
				display: none;
			}
			.logo-lg{
				display: block;
				.b{
					font-weight: 700;
				}
			}
		}
	}
	.navbar-custom-menu{
		>.navbar-nav{
			>li{
				position: relative;
			}
		}
	}
	.navbar-nav>li>a{
		padding-top: 10px;
		padding-bottom: 10px;
		line-height: 20px;
	}
	.nav{
		li{
			position: relative;
			display: block;
			list-style: none;
			cursor: pointer;
			a{
				position: relative;
				display: block;
				padding: 10px 15px;
			}
		}
		>li>a{
			position: relative;
			display: block;
			padding: 10px 15px;
			>img{
				max-width: none;
			}
		}
	}
	image{
		vertical-align: middle;
		border: 0;
		display: inline-block;
	}
	.navbar-custom-menu>.navbar-nav>li>.dropdown-menu{
		position: absolute;
		right: 0;
		left: auto;
	}
	.navbar-nav>.user-menu>.dropdown-menu{
	    border-bottom-right-radius: 4px;
	    border-bottom-left-radius: 4px;
		border-top-right-radius: 0;
		border-top-left-radius: 0;
		padding: 1px 0 0 0;
		width: 280px;
	}
	.navbar-nav>li>.dropdown-menu{
		margin-top: 0;
		box-shadow: none;
	}
	.dropdown-menu{
		position: absolute;
		top: 100%;
		left: 0;
		z-index: 300;
		display: none;
		float: left;
		min-width: 160px;
		padding: 5px 0;
		margin: 2px 0 0;
		font-size: 14px;
		text-align: left;
		list-style: none;
	}
	.message-bell-btn{
		font-size: 18px;
	    cursor: pointer;
	    width: 30px;
	    height: 30px;
	    display: inline;
	    line-height: 30px;
	    text-align: center;
	    margin-left: 10px;
	}
	.message-bell-btn:hover{
		color: #999;
	}
	.message-bell{
		.badge-dot{
			top: -10px;
			left: -5px;
			width: 8px;
			height: 8px;
			padding: 0;
			border-radius: 50%;
			position: relative;
		    display: inline-block;
		    font-size: 12px;
		    text-align: center;
		    background-color: #FF5722 !important;
		    color: #fff;
		    line-height: 16px;
			border: 1px solid black;
		}
	}
	.navbar-nav>.user-menu .user-image {
	    float: left;
	    width: 25px;
	    height: 25px;
	    border-radius: 50%;
	    margin-right: 10px;
	    margin-top: -2px;
	}
	.main-header{
		.navbar-custom-menu{
			float: right;
		}
	}
	
	.user-menu.open{
		.dropdown-menu{
			display: block;
		}
		background: rgba(0,0,0,0.1);
		color: #f6f6f6;
	}
	
	//适配两种屏幕 min-width:768px
	.wrapper.sidebar-collapse{
		@media (min-width:768px) {
			.main-header{
				.logo{
					width: 30px;
				}
			}
		}
	}
</style>