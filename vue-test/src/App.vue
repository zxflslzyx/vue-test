<template>
	<div id="app">
		<transferCanvas />
	</div>
</template>

<script>
import transferCanvas from "@/components/canvas/transferCanvas.vue";
import nodeReq from "@/components/nodeReq.vue"; // 配合node爬虫测试

export default {
	name: "App",
	data() {
		return {
		};
	},
	components: {
		transferCanvas
	},
	mounted() {
	},
	computed: {
		isShowList() {
			return this.$store.state.isShowList;
		}
	},
	methods: {
		preventEvent() {
			console.log('test');
		},
		changeScreen() {
			let w = window.innerWidth;
			let h = window.innerHeight;
			this.isHorizon = w > h;
			let isLongScreen = 1.8 * w < h;
			this.$store.commit('changeScreen', isLongScreen);
		}
	}
};
</script>

<style lang="less">
@import "./swiper.min.css";
.img {
  width: 100%;
  height: 100%;
}
</style>