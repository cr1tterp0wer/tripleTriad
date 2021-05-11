<template>
	<div class="tCard" v-click='this.select'>
		<img class="tCardImg" :src='this.url' />
	</div>
</template>

<script>
import triadData from '@/data/Triple_Triad.json';
export default {
	name: "Card",
	props: {
		cardID: Number
	},
	data() {
		return {
			ID: this.cardID,
			attackPower: {
				UP: 1,
				DOWN: 2,
				LEFT: 3,
				RIGHT: 4
			},
			url: ''
		};
	},
	methods: {
		clicked() {
		}
	},
	mounted() {
		this.globalDeck = triadData.results;
		this.url = this.globalDeck[this.ID - 1].image;
	}
};
</script>

<style lang="scss">
.tCard,
.tCardImg {
	cursor: pointer;

	&:hover{
		height: 100%;
	}
}
</style>
