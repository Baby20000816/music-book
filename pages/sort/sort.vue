<template>
	<view class="content">
		<search-box class="cal"></search-box>
		<view class="cal" style="height: 20rpx;"></view>
		<view class="flex" style="background-color: #f0f3f8;">
			<scroll-view
				scroll-y
				class="font text-light-black"
				style="width: 180rpx;padding: 0 20rpx;"
				:style="{ height: `${calHeight}rpx` }"
			>
				<block v-for="(item, index) in leftListRes" :key="index">
					<view
						class="animated faster"
						:class="leftIndex === index ? 'font-weight-bold' : ''"
						style="height: 150rpx;line-height: 150rpx;"
						@tap="leftToright(index)"
					>
						{{ item }}
					</view>
				</block>
			</scroll-view>

			<scroll-view
				scroll-y
				:scroll-into-view="rightIndex"
				scroll-with-animation
				:style="{ height: `${calHeight}rpx` }"
				@scroll="rightToleft"
			>
				<block v-for="(item, index) in rightListRes" :key="index">
					<view style="height: 250rpx;margin-bottom: 70rpx;" :id="`right${index}`">
						<view class="text-center" style="height: 80rpx;line-height: 80rpx;">
							<text class="mr-1">{{ item.text }}</text>
							<my-icon iconId="icon-youjiantou" iconSize="40"></my-icon>
						</view>

						<view class="flex flex-wrap bg-white rounded font" style="height: 170rpx;">
							<block v-for="(mitem, mindex) in item.content" :key="mindex">
								<view class="flex align-center justify-center" style="width: calc(100%/3);">
									{{ mitem }}
								</view>
							</block>
						</view>
					</view>
				</block>
			</scroll-view>
		</view>
	</view>
</template>

<script>
import { sortResources as resources } from './sortResources';
import $U from '@/common/unit';
import searchBox from '@/components/searchBox.vue';
export default {
	data() {
		return {
			statusBarHeight: this.$statusBarHeight,
			calHeight: 0,
			leftIndex: 0,
			rightIndex: `right${0}`
		};
	},
	components: {
		searchBox
	},
	computed: {
		leftListRes() {
			let res = resources.map(item => item.text);
			return res;
			console.log(res)
		},
		rightListRes() {
			return resources;
		}
	},
	methods: {
		leftToright(i) {
			this.rightIndex = `right${i}`;
		},
		rightToleft(e) {
			let curScrollTop = e.detail.scrollTop,
				standardVal = $U.Topx(320),
				curIndex = Math.round(curScrollTop / standardVal);
			this.leftIndex = curIndex;
		}
	},
	mounted() {
		$U.calSurplusHeight({
			pageID: this,
			pos: 'cal',
			isTabBarPage: true,
			success: val => (this.calHeight = val)
		});
	}
};
</script>

<style>
.selected {
	color: #f7646d;
}
</style>
