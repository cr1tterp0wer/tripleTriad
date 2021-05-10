<template>
	<div class="tCard">
		<img class="tCardImg" :src='this.url' />
	</div>
</template>

<script>
export default {
	name: "Card",
	data() {
		return {
			ID: 0,
			attackPower: {
				UP: 1,
				DOWN: 2,
				LEFT: 3,
				RIGHT: 4
			},
			url: 'https://picsum.photos/seed/picsum/200/300'
		};
	}
};
</script>

<style lang="scss">
.tCard,
.tCardImg {
	width: 100%;
	height: 100%;
}
</style>
