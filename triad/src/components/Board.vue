<template>

	<div class="GameBoard">

		<div class="tPlayerOne playerHand">
			<div class="playerBoard">
				<div class="cardStats">
					<div></div>
					<div></div>
					<div></div>
					<div></div>
				</div>
				<ul id="tPlayerOneHand">
					<li v-for="(card, index) in playerOne" v-bind:key="index">
						<Card :key="index" :cardID="card"></Card>
					</li>
				</ul>
			</div>
		</div>

		<div class="tBoard">

			<div class="tSocket space1"></div>
			<div class="tSocket space2"></div>
			<div class="tSocket space3"></div>

			<div class="tSocket space4"></div>
			<div class="tSocket space5"></div>
			<div class="tSocket space6"></div>

			<div class="tSocket space7"></div>
			<div class="tSocket space8"></div>
			<div class="tSocket space9"></div>

		</div>

		<div class="tPlayerTwo playerHand">
			<ul id="tPlayerTwoHand">
				<li v-for="(card, index) in playerTwo" v-bind:key="index">
					<Card :key="index" :cardID="card"></Card>
				</li>
			</ul>
		</div>

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
	data() {
		return {
			playerOne: [],
			playerOneSelectedIndex: 0,
			playerTwo: []
		};
	},
	mounted() {
		this.initPlayers();
	},
	methods: {
		initPlayers() {
			//grab the data
			this.globalDeck = triadData.results;
			let max = this.globalDeck.length;

			for (let i = 0; i < 5; i++) {
				this.playerOne[i] = Math.floor(Math.random() * max);
				this.playerTwo[i] = Math.floor(Math.random() * max);
			}
		}
	}
};
</script>

<style lang="scss">
$ratio: 0.7142857143;
$cardHeight: 200px;
$cardWidth: $cardHeight * $ratio;

.GameBoard {
	display: grid;
	grid-template-columns: 1fr 3fr 1fr;
	grid-gap: 20px;

	.playerHand {
		ul {
			display: grid;
			list-style: none;
			margin: 0;
			padding: 0;

			li {
				max-height: 100px;
			}
		}
	}
}

.tBoard {

	display: grid;
	margin: 0 auto;
	grid-gap: 10px;
	grid-template-columns: repeat(3, $cardWidth);
	grid-template-rows: repeat(3, $cardHeight);

	.tSocket {
		background: #990033;
		background: rgba(1,1,1,0.06);
		border: 1px solid rgba(1,1,1,0.1);
		border-radius: 20px;
		box-shadow: inset 3px 3px 11px;
		width: 100%;
		height: 100%;

	}

}
</style>
