<template>
	<header class="bg-white px-12 w-full flex items-center justify-between">
		<h1 class="tracking-widest text-xl">ОЛИМП КЛИНИК</h1>
		<SearchInput />
		<Buttons />
		<button class="sm:hidden" @click="onClickBurger">
			<img src="../assets/menu.png" alt="menu">
		</button>
	</header>
</template>

<script>
import SearchInput from './SearchInput'
import Buttons from './Buttons'


export default {
	name: 'Header',
	components: { SearchInput, Buttons },
	props: {
		onClickBurger: { type: Function },
		isVisibleMobileNavigation: { type: Boolean }
	}
}
</script>

<style>
</style>