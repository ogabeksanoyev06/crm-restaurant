<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/autoplay';
import 'swiper/css/pagination';
import 'swiper/css/effect-fade';
import { Autoplay, Pagination, EffectFade } from 'swiper/modules';
import { useMediaQuery } from '@vueuse/core';
const isDesktop = useMediaQuery('(min-width: 768px)');

const props = defineProps({
	product: {
		type: Object,
		default: () => ({
			title: { uz: 'Mahsulot nomi' },
			description: { uz: 'Mahsulot tavsifi' },
			out_price: 0,
			currency: "so'm",
			discountPrice: null
		})
	}
});

const settings = {
	loop: true,
	autoplay: {
		delay: 3000,
		disableOnInteraction: false
	},
	delay: 3000,
	slidesPerView: 1,
	spaceBetween: 12,
	pagination: {
		clickable: true
	},
	effect: 'fade'
};

const isOpen = ref(false);
</script>
<template>
	<div class="group flex flex-col overflow-hidden rounded-xl shadow-md hover:shadow-lg transition-shadow duration-300 ease-in-out">
		<div>
			<Swiper ref="swiperRef" v-bind="settings" :modules="[Autoplay, Pagination, EffectFade]" class="product-slider">
				<SwiperSlide v-for="item in 5" class="relative aspect-square">
					<CommonImage :src="`https://tarnov.uz/_next/image?url=https%3A%2F%2Fcdn.delever.uz%2Fdelever%2F${product.image}&w=1920&q=75`" :alt="product.title.uz" class="object-contain w-full h-full" />
				</SwiperSlide>
			</Swiper>
		</div>
		<div class="flex flex-1 flex-col p-1.5 sm:p-4">
			<h3 class="line-clamp-1 sm:text-lg font-semibold" @click="isOpen = true">{{ product?.title?.uz }}</h3>
			<p class="line-clamp-1 text-xs sm:text-sm text-foreground/60">
				{{ product?.description?.uz }}
			</p>
			<div class="flex justify-between items-center my-2">
				<div class="flex flex-col">
					<span class="line-through text-muted-foreground text-xs" v-if="product?.discountPrice"> 120 000 </span>
					<span class="text-sm font-medium">
						{{ formatPrice(product?.out_price) }} <span>{{ product?.currency }}</span>
					</span>
				</div>
				<button @click="isOpen = true" class="w-8 h-8 p-1 rounded-full flex items-center justify-center border">
					<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="">
						<path
							d="M8 10V8H6V12.5C6 12.7761 5.77614 13 5.5 13C5.22386 13 5 12.7761 5 12.5V7H8C8 4.59628 9.95227 3 12 3C14.0575 3 16 4.70556 16 7H19V19.5C19 20.3284 18.3284 21 17.5 21H12.5C12.2239 21 12 20.7761 12 20.5C12 20.2239 12.2239 20 12.5 20H17.5C17.7761 20 18 19.7761 18 19.5V8H16V10H15V8H9V10H8ZM12 4C10.4477 4 9 5.20372 9 7H15C15 5.29444 13.5425 4 12 4Z"
							fill="currentColor"
						></path>
						<path
							d="M7.5 14C7.77614 14 8 14.2239 8 14.5V17H10.5C10.7761 17 11 17.2239 11 17.5C11 17.7761 10.7761 18 10.5 18H8V20.5C8 20.7761 7.77614 21 7.5 21C7.22386 21 7 20.7761 7 20.5V18H4.5C4.22386 18 4 17.7761 4 17.5C4 17.2239 4.22386 17 4.5 17H7V14.5C7 14.2239 7.22386 14 7.5 14Z"
							fill="currentColor"
						></path>
					</svg>
				</button>
			</div>
			<div class="mt-auto">
				<Button class="rounded-xl w-full">
					Savatga qo'shish
					<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-plus">
						<path d="M5 12h14" />
						<path d="M12 5v14" />
					</svg>
				</Button>
				<NumberField :default-value="1" :min="1" v-if="false">
					<NumberFieldContent>
						<NumberFieldDecrement />
						<NumberFieldInput class="rounded-xl" />
						<NumberFieldIncrement />
					</NumberFieldContent>
				</NumberField>
			</div>
		</div>
		<ClientOnly>
			<Dialog v-if="isDesktop" v-model:open="isOpen">
				<DialogContent class="sm:max-w-[525px] p-0 max-h-[90vh]">
					<DialogHeader class="p-4 pb-0">
						<DialogTitle>{{ product?.title?.uz }}</DialogTitle>
					</DialogHeader>
					<div class="grid gap-4 px-4 overflow-y-auto">
						<div class="relative max-w-[350px] mx-auto w-full">
							<CommonImage :src="`https://tarnov.uz/_next/image?url=https%3A%2F%2Fcdn.delever.uz%2Fdelever%2F${product.image}&w=1920&q=75`" :alt="product.title.uz" class="object-contain w-full h-full" />
						</div>
						<div class="flex flex-1 flex-col gap-1 pb-4">
							<h3 class="line-clamp-1 text-lg font-semibold">
								{{ formatPrice(product?.out_price) }} <span>{{ product?.currency }}</span>
							</h3>
							<p class="text-sm text-foreground/60">
								{{ product?.description?.uz }}
							</p>
						</div>
					</div>
					<DialogFooter class="gap-2 p-4">
						<Button class="rounded-xl w-full">
							Savatga qo'shish
							<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-plus">
								<path d="M5 12h14" />
								<path d="M12 5v14" />
							</svg>
						</Button>
						<NumberField class="w-full" :default-value="1" :min="1">
							<NumberFieldContent>
								<NumberFieldDecrement />
								<NumberFieldInput class="rounded-xl" />
								<NumberFieldIncrement />
							</NumberFieldContent>
						</NumberField>
					</DialogFooter>
				</DialogContent>
			</Dialog>
			<Drawer v-else v-model:open="isOpen">
				<DrawerContent class="max-h-[90dvh]">
					<DrawerHeader class="text-left p-4">
						<DrawerTitle>Zig'ir oshi komplekt</DrawerTitle>
					</DrawerHeader>
					<div class="grid gap-4 px-4 h-full overflow-y-auto">
						<div class="relative max-w-[350px] mx-auto w-full">
							<CommonImage :src="`https://tarnov.uz/_next/image?url=https%3A%2F%2Fcdn.delever.uz%2Fdelever%2F${product.image}&w=1920&q=75`" :alt="product.title.uz" class="object-contain w-full h-full" />
						</div>
						<div class="flex flex-1 flex-col gap-1 pb-4">
							<h3 class="line-clamp-1 text-lg font-semibold">60 500 so'm</h3>
							<p class="text-sm text-foreground/60">
								Samarqand zigi'r oshini tatib ko'ring! O'zgacha to'g'ralgan go‘sht, xushbo‘y ziravorlar va zig'ir yog'i o'ziga xos ta'mga ega nafis taom yaratadi. Hoziroq buyurtma bering va Samarqandning haqiqiy kulinariya asaridan bahramand bo'ling!
							</p>
						</div>
					</div>
					<DrawerFooter class="pt-2 px-4">
						<Button class="rounded-xl w-full">
							Savatga qo'shish
							<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-plus">
								<path d="M5 12h14" />
								<path d="M12 5v14" />
							</svg>
						</Button>
						<NumberField class="w-full" :default-value="1" :min="1">
							<NumberFieldContent>
								<NumberFieldDecrement />
								<NumberFieldInput class="rounded-xl" />
								<NumberFieldIncrement />
							</NumberFieldContent>
						</NumberField>
					</DrawerFooter>
				</DrawerContent>
			</Drawer>
		</ClientOnly>
	</div>
</template>

<style>
.product-slider .swiper-pagination-bullet {
	transition: all 0.3s;
	background-color: #fff !important;
	width: 24px;
	height: 2px;
	border-radius: 8px;
}
.product-slider .swiper-pagination-bullet-active {
	background-color: #fff !important;
	width: 32px;
}
</style>
