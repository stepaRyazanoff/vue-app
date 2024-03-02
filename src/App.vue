<template>
	<div class="app">
		<div class="app__inner">
			<div class="app__header">
				<h3 class="app__title">Invictus</h3>
				<p class="app__author">By William Ernest Henley</p>
			</div>
			<div class="app__content">
				<div class="app__buttons">
					<button
						class="app__btn"
						@click="toggleElementVisibility($event, 'isFirstElVisible')"
						:disabled="!isSecondElVisible && !isThirdElVisible && !isFourthElVisible"
					></button>
					<button
						class="app__btn"
						@click="toggleElementVisibility($event, 'isSecondElVisible')"
						:disabled="!isFirstElVisible && !isThirdElVisible && !isFourthElVisible"
					></button>
					<button
						class="app__btn"
						@click="toggleElementVisibility($event, 'isThirdElVisible')"
						:disabled="!isFirstElVisible && !isSecondElVisible && !isFourthElVisible"
					></button>
					<button
						class="app__btn"
						@click="toggleElementVisibility($event, 'isFourthElVisible')"
						:disabled="!isFirstElVisible && !isSecondElVisible && !isThirdElVisible"
					></button>
				</div>
				<ul class="app__list-items">
					<li class="app__list-item">
						<FirstComponent v-if="isFirstElVisible" />
					</li>
					<li class="app__list-item">
						<SecondComponent v-if="isSecondElVisible" />
					</li>
					<li class="app__list-item">
						<ThirdComponent v-if="isThirdElVisible" />
					</li>
					<li class="app__list-item">
						<FourthComponent v-if="isFourthElVisible" />
					</li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
import FirstComponent from './components/FirstComponent.vue'
import SecondComponent from './components/SecondComponents.vue'
import ThirdComponent from './components/ThirdComponent.vue'
import FourthComponent from './components/FourthComponent.vue'

export default {
	components: {
		FirstComponent,
		SecondComponent,
		ThirdComponent,
		FourthComponent,
	},
	data() {
		return {
			isFirstElVisible: true,
			isSecondElVisible: true,
			isThirdElVisible: true,
			isFourthElVisible: true,
		}
	},
	methods: {
		toggleElementVisibility(e, propertiesName) {
			e.target.classList.toggle('hidden')
			this[propertiesName] = !this[propertiesName]
			return this[propertiesName]
		},
	},
}
</script>

<style>
.app {
	padding: 20px 0 40px 0;
	margin-bottom: 100px;
}

.app__header {
	display: flex;
	justify-content: center;
	align-items: baseline;
	margin-bottom: 10px;
}

.app__title {
	font-size: 64px;
	font-weight: 500;
	position: relative;
	flex-basis: 620px;
	text-align: right;
}

.app__author {
	font-size: 32px;
	margin-left: 85px;
}

.app__content {
	display: flex;
	justify-content: center;
}

.app__buttons {
	flex-basis: 320px;
}

.app__btn {
	width: 40px;
	height: 40px;
	background-color: black;
	border: transparent;
}

.app__btn {
	margin-right: 40px;
}

.app__list-items {
	flex-basis: 900px;
	font-size: 40px;
}

.indented-line {
	display: inline-block;
	margin-left: 60px;
}

.hidden {
	background-color: transparent;
	border: 1px solid black;
}

@media (max-width: 1250px) {
	.app__buttons {
		display: flex;
		flex-direction: column;
		align-items: center;
		flex-basis: 200px;
	}

	.app__btn {
		margin: 0 0 40px;
	}

	.app__list-items {
		flex-basis: 780px;
	}
}

@media (max-width: 1071px) {
	.app__header {
		display: block;
	}

	.app__title {
		text-align: center;
	}

	.app__inner {
		position: relative;
		padding-bottom: 100px;
	}

	.app__author {
		position: absolute;
		bottom: 0;
		right: 20px;
		margin: 0;
	}

	.app__buttons {
		flex-basis: 150px;
	}

	.app__list-items {
		flex-basis: 740px;
	}
}

@media (max-width: 800px) {
	.app__header {
		margin-bottom: 5px;
	}

	.app__title {
		font-size: 42px;
		flex-basis: 552px;
	}

	.app__author {
		font-size: 21px;
		bottom: 20px;
	}

	.app__buttons {
		flex-basis: 100px;
	}

	.app__btn {
		width: 25px;
		height: 25px;
	}

	.app__btn:not(:last-child) {
		margin-bottom: 20px;
	}

	.app__list-items {
		flex-basis: 552px;
		font-size: 30px;
	}

	.indented-line {
		margin-left: 45px;
	}
}

@media (max-width: 683px) {
	.app__title {
		font-size: 32px;
	}

	.app__author {
		font-size: 16px;
		right: 110px;
		bottom: 60px;
	}

	.app__buttons {
		flex-basis: 70px;
		align-items: center;
	}

	.app__btn {
		width: 20px;
		height: 20px;
	}

	.app__list-items {
		flex-basis: 368px;
		font-size: 20px;
	}

	.indented-line {
		margin-left: 30px;
	}
}
</style>
