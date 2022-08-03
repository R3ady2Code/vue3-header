<template>
	<div class="sm:hidden flex flex-col items-start bg-white p-6">
		<div class="bg-gray-100 w-full flex items-center justify-between">
			<input type="text" placeholder="Поиск по сайту..."
				class="bg-gray-100 text-lg outline-none text-gray-600 p-4 w-full rounded">
			<img src="../assets/search.png" class="p-4 border-l-2" alt="">
		</div>
		<nav class="flex flex-col items-start py-4">
			<a v-for="category, i in categories" :key="i" class="text-lg mb-4">{{ category }}</a>
		</nav>
		<div class="flex items-center">
			<button class="p-3.5 text-lg rounded border border-black mr-3">Обратный звонок</button>
			<button class="py-4 px-6 text-lg rounded border border-black">
				<img src="../assets/user.svg" alt="user">
			</button>
		</div>
	</div>
</template>

<script>
export default {
	name: 'MobileNav',
	data: () => ({
		categories: ['Направления', 'Специалисты', 'Предложения', 'Клиники', 'Аппараты', 'Пациентам', 'Новости и медиа', 'О клинике']
	})
}
</script>