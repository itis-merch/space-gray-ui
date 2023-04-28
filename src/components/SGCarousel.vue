<template>
	<div class="carousel">
		<div class="carousel-inner">
			<SGCarouselIndicators
					:total="slides.length"
					:current-index="currentSlide"
					@switch="switchSlide($event)"
			></SGCarouselIndicators>
			<SGCarouselItem
					v-for="(slide, index) in slides"
					:slide="slide"
					:key="`item-${index}`"
					:current-slide="currentSlide"
					:index="index"
					:direction="direction"
			>
			</SGCarouselItem>
		</div>
	</div>
</template>

<script>
import SGCarouselItem from "@/components/SGCarouselItem.vue";
import SGCarouselIndicators from "@/components/SGCarouselIndicators.vue";
export default {
	components: {
		SGCarouselItem,
		SGCarouselIndicators
	},
	props: {
		slides: {
			type: Array,
			required: true
		}
	},
	data () {
		return {
			interval: 7000,
			currentSlide: 0,
			slideInterval: null,
			direction: "right",
		}
	},
	methods: {
		setCurrentSlide(index) {
			this.currentSlide = index;
		},
		prev(step = -1) {
			const index =
				this.currentSlide > 0
					? this.currentSlide + step
					: this.slides.length - 1;
			this.setCurrentSlide(index);
			this.direction = "left";
			this.startSlideTimer();
		},
		_next(step = 1) {
			const index =
				this.currentSlide < this.slides.length - 1
					? this.currentSlide + step
					: 0;
			this.setCurrentSlide(index);
			this.direction = "right";
		},
		next(step = 1) {
			this._next(step);
			this.startSlideTimer();
		},
		startSlideTimer() {
			this.stopSlideTimer();
			this.slideInterval = setInterval(() => {
				this._next();
			}, this.interval);
		},
		stopSlideTimer() {
			clearInterval(this.slideInterval);
		},
		switchSlide(index) {
			const step = index - this.currentSlide;
			if (step > 0) {
				this.next(step);
			} else if (step < 0) {
				this.prev(step);
			}
		},
	},
	mounted() {
		this.startSlideTimer();
	},
	beforeUnmount() {
		this.stopSlideTimer();
	},
}
</script>

<style scoped>
.carousel {
	display: flex;
	justify-content: center;
}
.carousel-inner {
	position: relative;
	width: 500px;
	height: 280px;
	overflow: hidden;
}
</style>