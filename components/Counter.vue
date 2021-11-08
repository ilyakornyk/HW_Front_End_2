<template>
	<div>
		<p class="fs-3 offset-4">Enter a number in range from 0 to 20</p>
		<div class="container text-center">
			<h3 class="mt-3 pb-3 fs-1" :class="{'text-danger': devidedByThree, 'text-success': devidedByFive}">{{counter}}</h3>
			<div class="input-group mb-3 col-md-6 offset-3">
				<span class="input-group-text" id="inputGroup-sizing-lg">Enter a number</span>
				<input type="text" @keypress.enter="submitCounter" class="form-control" aria-label="Sizing example input" aria-describedby="inputGroup-sizing-lg">
			</div>
			<button class="btn btn-lg btn-success"  @click="addCounter" :class="{disabled: greaterThan}">+</button>
			<button class="btn btn-lg btn-danger"  @click="substractCounter" :class="{disabled: lessThan}" > -</button>
	</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			counter: 0,
			greaterThan: false,
			lessThan: false,
			devidedByFive: false,
			devidedByThree: false
		}
	},
	methods: {
		addCounter () {
			if (this.isGreaterThan()) {
				this.counter++;
			}
		},
		substractCounter() {
			if (this.isLessThan()) {
				this.counter--;
			}
		},
		isGreaterThan() {
			if (this.counter >= 20) {
				this.greaterThan = true
				return false
			} else {
				this.greaterThan = false
				return true
			}
		},
		isLessThan() {
			if (this.counter === 0) {
				this.lessThan = true
				return false
			} else {
				this.lessThan = false
				return true
			}
		},
		submitCounter(e) {
			if (e.target.value > 0  && e.target.value < 20) {
				this.counter = e.target.value;
				e.target.value = ''
			}
		}
	},
	watch: {
		counter () {
			if (this.counter % 5 == 0) {
				this.devidedByThree = false;
				this.devidedByFive = true;
			} else if (this.counter % 3 === 0) {
				this.devidedByFive = false;
				this.devidedByThree = true;
			} else {
				this.devidedByThree = false;
				this.devidedByFive = false;
			}
		}
	},
	created() {
		if (this.counter === 0) {
			this.lessThan = true
		} else {
			this.greaterThan = true
		}
	},
	beforeUpdate() {
		if(this.counter > 0 && this.counter < 20) {
			this.lessThan = false
			this.greaterThan = false
		}
	}
}
</script>

<style>
	.btn {
		font-size: 32px;
		width: 60px;
		height: 60px;
	}
</style>