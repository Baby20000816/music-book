<template>
	<div class="box">
		<div style="flex:0 0 40%; height: 100%; display: flex; align-content: center;">
			<img
				style="width: 100%; height: 400px; margin:auto; border-radius: 8px;"
				src="../../static/tabbar/1.jpg"
				alt=""
			/>
		</div>

		<div
			style="flex:0 0 30%; margin-left: 40px; display: flex; justify-content: center; align-items: flex-start; flex-direction: column; margin-top: -20rpx;"
		>
			<div style="margin-bottom: 10px;"><span class="title">管理员登陆</span></div>
			<div
				style="display: flex; justify-content: space-between; width: 100%; align-items: flex-end; height: 60px; border-bottom: 2px solid white;"
			>
				<p class="font" style="margin-bottom: 20px;">请使用账号密码或人脸登录</p>
				<img
					src="../../static/tabbar/menu.png"
					style="width: 50px; height: 50px; margin-bottom: 10px;"
					alt=""
				/>
			</div>
			<div style="display: flex; flex-direction: column; width: 100%;">
				<input
					type="text"
					placeholder="USERNAME"
					style="padding-left: 10px; height: 50px; width: 100%; margin-top: 30px; border-radius: 5px; outline: none; border: none;background-color: #FFFFFF;"
				/>
				<input
					type="password"
					placeholder="PASSWORD"
					style="padding-left: 10px; height: 50px; width: 100%; margin-top: 30px; border-radius: 5px; outline: none; border: none;background-color: #FFFFFF;"
				/>
			</div>
			<div
				style="display: flex; justify-content: space-between; width: 100%; align-items: center; margin-top: 20px;"
			>
				<div style="display: flex;">
					<text class="font">
						<checkbox />
					人脸识别登录</text>
				</div>
				<div class="font1">建议在Chorem下使用本系统</div>
			</div>
			<Button class="login-btn">戳我登录</Button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'index'
};
</script>

<style scoped>
.box {
	display: flex;
	justify-content: center;
	align-items: center;
	position: absolute;
	left: 0;
	top: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(106, 61, 95, 0.8);
	background-image: url(../../static/tabbar/3.jpg);
}

.title {
	font-size: 36px;
	font-weight: bold;
	color: white;
}

.font {
	font-size: 16px;
	color: rgb(232, 232, 232);
}

.font1 {
	font-size: 14px;
	color: #eeeeee;
}

.login-btn {
	width: 100%;
	height: 50px;
	margin-top: 10px;
	color: white;
	outline: none;
	border: none;
	border-radius: 5px;
	background-color: #8dcdb9;
}
</style>
