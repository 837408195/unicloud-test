<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{ title }}</text>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			title: 'Hello'
		};
	},
	async onLoad() {
		uniCloud
			.callFunction({
				name: 'list',
				data: {}
			})
			.then(res => {
				console.log('成功', res);
			})
			.catch(res => {
				console.log('异常', res);
			})
			.finally(res => {
				console.log('最终', res);
			});
			
		// uniCloud.callFunction({
		// 	name: 'list',
		// 	data: {},
		// 	success(res) {
		// 		console.log('成功', res);
		// 	},
		// 	fail(res) {
		// 		console.log('失败', res);
		// 	},
		// 	complete(res) {
		// 		console.log('完成', res);
		// 	}
		// });
		// const db = uniCloud.database()
		// const userCollection = db.collection('user')
		// // const res = await userCollection.get()
		// userCollection.get().then(res=>{
		// 	console.log('前端调用数据库',res);
		// }).finally(res=>{
		// 	console.log('完成',res);
		// })
	},
	methods: {}
};
</script>

<style>
.content {
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}

.logo {
	height: 200rpx;
	width: 200rpx;
	margin-top: 200rpx;
	margin-left: auto;
	margin-right: auto;
	margin-bottom: 50rpx;
}

.text-area {
	display: flex;
	justify-content: center;
}

.title {
	font-size: 36rpx;
	color: #8f8f94;
}
</style>
