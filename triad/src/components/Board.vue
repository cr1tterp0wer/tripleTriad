<template>
	<div class="tBoard">

		<div class="tSocket space1"><Card></Card></div>
		<div class="tSocket space2"></div>
		<div class="tSocket space3"></div>

		<div class="tSocket space4"></div>
		<div class="tSocket space5"></div>
		<div class="tSocket space6"><Card></Card></div>

		<div class="tSocket space7"></div>
		<div class="tSocket space8"></div>
		<div class="tSocket space9"></div>

	</div>
</template>

<script>
import triadData from '@/data/Triple_Triad.json';
import Card from '@/components/Card';
export default {
	name: "Board",
	components: {
		Card
	},
	created() {
		//grab the data
		this.globalDeck = triadData.results;
		console.log(this.globalDeck);
	},
};
</script>

<style lang="scss">
.tBoard {
	$ratio: 0.7142857143;
	$cardHeight: 200px;
	$cardWidth: $cardHeight * $ratio;

	display: grid;
	margin: 0 auto;
	grid-gap: 10px;
	grid-template-columns: repeat(3, $cardWidth);
	grid-template-rows: repeat(3, $cardHeight);

	.tSocket {
		background: blue;
		width: 100%;
		height: 100%;
	}

}
</style>
