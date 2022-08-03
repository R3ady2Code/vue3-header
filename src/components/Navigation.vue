<template>
	<div class="bg-white px-12 pt-2 pb-4 hidden sm:block">
		<nav class="flex w-full xl:w-4/5 justify-between ">
			<a v-for=" (category, i) in categories" :key="i"
				class="text-xs text-center sm:text-sm lg:text-lg xl:text-xl cursor-pointer">{{
						category
				}}</a>
		</nav>
	</div>
</template>

<script>
export default {
	name: 'Navigation',
	data: () => ({
		//таким образом удобнее добавлять/удалять категории в навигации
		categories: ['Направления', 'Специалисты', 'Предложения', 'Клиники', 'Аппараты', 'Пациентам', 'Новости и медиа', 'О клинике']
	})
}
</script>