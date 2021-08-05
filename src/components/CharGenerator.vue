<template>
	<div id="charGenerator">
		<div 
			v-for="(char, charIndex) in characters"
			:key="'char' + charIndex"
			class="charCards"
			v-show="charIndex === selectedIndex" 
		>	
			<div class="card">
				<div class="charImgContainer">
					<img 
						:src="require(`@/assets/${char.imgSrc}`)" 
						class="charImg"
					/>
				</div>

				<div class="container">
					<h2>{{ char.name }}</h2>
					<p><b>Birthday:</b> {{ char.bday }}</p>
					<p v-if="char.quote">"{{ char.quote }}"</p>
				</div>
			</div>
		</div>
		
		<div>
			<button @click="chooseCharacter">
				<div id="chooseCharButton">choose character</div>
			</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'CharGenerator',
	data() {
		return {
			characters: [
				{name: "Omori", bday: '7/20', quote: "", imgSrc: "Omori.jpg"},
				{name: "Sunny", bday: '7/20', quote: "", imgSrc: "Sunny.jpg"},
				{name: "Basil", bday: '2/18', quote: "I just finished planting some little sprouts and wanted to show everyone.", imgSrc: "Basil.png"},
				{name: "Mari", bday: '3/1', quote: "How could someone hate bunnies!? I just don't understand some people...", imgSrc: "Mari.jpg"},
				{name: "Kel", bday: '11/11', quote: "Just because you did something bad, doesn't make you a bad person.", imgSrc: "Kel.png"},
				{name: "Hero", bday: '1/1', quote: "I'm glad that's all settled. Those two always seem to be bumpingheads.", imgSrc: "Hero.jpg"},
				{name: "Aubrey", bday: '5/23', quote: "We were hoping that you'd come by soon! Wanna play cards with us?", imgSrc: "Aubrey.png"}
			],
			selectedIndex: 0
		}
	},
	methods: {
		generateRandomInt(min, max) { 
			return Math.floor(Math.random() * (max - min + 1) + min)
		},
		chooseCharacter() {
			this.selectedIndex = this.generateRandomInt(0, 6);
		}
	}
}
</script>

<style>
button {
	background: white;
	padding: 4px;
	border: 1px solid black;
	font-family: 'Schoolbell', cursive;
	letter-spacing: .25em;
	font-size: 1.5em;
}

button:hover {
	transition: .3s ease;
	opacity: .8;
	cursor: pointer;
	user-select: none;
}

#charGenerator {
	width: 100%;
	height: 100%;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}

.charCards {
	width: 100%;
	display: flex;
	justify-content: center;
	margin-bottom: 1em;
}

.card {
	background: white;
	box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
	transition: 0.3s;
	width: 50%;
	max-width: 350px;
	border-radius: 4px;
	padding: 24px;
}

.card:hover {
	box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.charImgContainer {
	height: auto;
	max-height: 350px;
	overflow: hidden;
	border-radius: 4px;
}

.charImg {
	width: 100%;
}

.container {
	padding: 2px 16px;
	min-height: 184px;
}

#chooseCharButton {
	background: black;
	color: white;
	text-transform: uppercase;
	padding: 4px 12px;
}
</style>