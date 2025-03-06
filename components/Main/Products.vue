<script setup></script>

<template>
	<div class="mt-10">
		<div class="relative lg:gap-10 xl:grid xl:grid-cols-[1fr_350px]">
			<section class="grid gap-10">
				<div id="Pilaf" v-for="(item, key) in categories" :key>
					<h2 class="text-xl sm:text-2xl font-bold mb-6">{{ item.title.uz }}</h2>
					<div class="grid grid-cols-1 xs:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
						<CardProduct v-for="product in item.products" :key="product.id" :product="product" />
					</div>
				</div>
			</section>
			<MainCart />
		</div>
	</div>
</template>
