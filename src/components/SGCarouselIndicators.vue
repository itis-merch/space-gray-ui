<template>
	<div class="carousel-indicators">
		<button
				class="carousel-indicator-item"
				:class="{active: currentIndex === index}"
				v-for="(item, index) in total"
				:key="index"
				@click="$emit('switch', index)"
		></button>
	</div>
</template>

<script>
export default {
	emits: ["switch"],
	props: {
		total: {
			type: Number,
		},
		currentIndex: {
			type: Number,
		}
	}
}
</script>

<style scoped>
.carousel-indicators {
	position: absolute;
	transform: translateX(-50%);
	left: 50%;
	bottom: -0.43em;
	z-index: 2;
}
.carousel-indicator-item {
	padding: 0;
	width: 7px;
	height: 7px;
	border: none;
	background: #545454;
	opacity: .5;
	margin: 0.2em;
	border-radius: 50%;
	cursor: pointer;
}
.active {
	opacity: 1;
}
</style>