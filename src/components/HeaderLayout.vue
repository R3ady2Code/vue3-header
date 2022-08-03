<template>
	<div class="fixed top-0 left-0 w-full" @mouseover="mouseOverHeader" @mouseleave="mouseLeaveHeader">
		<Header class="duration-300" :class="{
			'py-6': isVisibleNavigation, 'py-4': !isVisibleNavigation
		}" :onClickBurger='onClickBurger' :isVisibleMobileNavigation='isVisibleMobileNavigation' />
		<transition name="slide-fade-nav">
			<Navigation class="duration-300" v-if="isVisibleNavigation" />
		</transition>
		<transition name="slide-fade-mobile">
			<MobileNav class="duration-300" v-if="isVisibleMobileNavigation" />
		</transition>
	</div>
</template>

<script>

import Header from './Header'
import Navigation from './Navigation'
import MobileNav from './MobileNav'

export default {
	name: 'HeaderLayout',
	components: {
		Header, Navigation, MobileNav
	},
	data: () => ({
		isVisibleNavigation: true,
		isVisibleMobileNavigation: false,
		mouseAtHeader: false //ввел переменную, для дэббага момента, когда при скорлле курсор находится на header
	}),
	mounted() {
		window.addEventListener('scroll', this.scrollPage, true)
	},
	methods: {
		scrollPage() {
			if (window.top.scrollY > 0 && !this.mouseAtHeader) {
				this.isVisibleNavigation = false
			} else this.isVisibleNavigation = true
		},
		mouseOverHeader() {
			if (window.top.scrollY !== 0) { //ввел логисечкую конструкцию if для предотвращения выполения действий наведения, при 0ой прокрутке страницы
				this.isVisibleNavigation = true
			}
			this.mouseAtHeader = true
		},
		mouseLeaveHeader() {
			if (window.top.scrollY !== 0) {
				this.isVisibleNavigation = false
			}
			this.mouseAtHeader = false
		},
		onClickBurger() {
			this.isVisibleMobileNavigation = !this.isVisibleMobileNavigation
		}
	}
}
</script>

<style>
.slide-fade-mobile-enter-from,
.slide-fade-mobile-leave-to {
	transform: translateX(20px);
	opacity: 0;
}

.slide-fade-nav-enter-from,
.slide-fade-nav-leave-to {
	transform: translateY(-20px);
	opacity: 0;
}
</style>