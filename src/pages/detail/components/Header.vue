<template>
	<div>
		<router-link tag="div" to="/" class="header-abs" v-show="showAbs">
			<div class="iconfont header-abs-back">&#xe744;</div>
		</router-link>
		<div class="header-fiexd" v-show="!showAbs" :style="opacityStyle">
			<router-link to="/">
				<div class="iconfont header-fiexd-back">&#xe744;</div>
			</router-link>
			景点详情
		</div>
	</div>
</template>

<script>
export default{
	name: 'DetailHeader',
	data () {
		return {
			showAbs: true,
			opacityStyle:{
				opacity: 0
			}
		}
	},
	methods: {
		handelScroll () {
			const top = document.documentElement.scrollTop
			if( top > 60 ){
				let opacity = top/140
				opacity = opacity > 1 ? 1: opacity
				this.opacityStyle = {opacity}
				this.showAbs = false
			}else{
				this.showAbs = true
			}
		}
	},
	activated () {
		window.addEventListener('scroll',this.handelScroll)
	},
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles'
	.header-abs
		position :absolute
		left :.2rem
		top :.2rem
		width :.8rem
		height :.8rem
		border-radius :.4rem
		background :rgba(0,0,0,.8)
		line-height :.8rem
	
	.header-abs-back
		color :#fff
		font-size :.4rem

	
	.header-fiexd
		z-index :2
		position :fixed
		top :0
		left :0
		right :0
		font-size :.32rem
		height :$headerHeight
		line-height :$headerHeight
		color :#fff
		background :$bgColor
		
	.header-fiexd-back
		position :absolute
		width :.64rem
		font-size :.4rem
		top :0
		left :0
		color :#fff

</style>
