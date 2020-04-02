<template>
	<div class="header">
		城市选择
		<router-link to="/">
			<div class="iconfont header-back">&#xe744;</div>
		</router-link>
	</div>
</template>

<script>
export default {
	name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles';
		
	.header{
		position :relative;
		overflow :hidden;
		font-size :.32rem;
		height :$headerHeight;
		line-height :$headerHeight;
		color :#fff;
		background :$bgColor
	}
	.header-back{
		position :absolute;
		width :.64rem;
		font-size :.4rem;
		top :0;
		left :0;
		color :#fff;
	}
</style>
