<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/autoplay';
import { Autoplay } from 'swiper/modules';

const swiperValue = ref(null);

const onSwiper = (swiper) => {
	swiperValue.value = swiper;
};

const settings = {
	loop: true,
	autoplay: {
		delay: 3000,
		disableOnInteraction: false
	},
	delay: 3000,
	slidesPerView: 1.3,
	spaceBetween: 12,
	centeredSlides: true,
	breakpoints: {
		640: {
			slidesPerView: 2,
			spaceBetween: 24
		},
		768: {
			slidesPerView: 3
		},
		1024: {
			slidesPerView: 4
		},
		1440: {
			slidesPerView: 5
		},
		1920: {
			slidesPerView: 6
		}
	}
};
</script>

<template>
	<div class="mt-10">
		<h1 class="section-title mb-6">Kategoriyalar</h1>

		<div class="overflow-hidden category-slider relative">
			<Swiper ref="swiperRef" @swiper="onSwiper" v-bind="settings" :modules="[Autoplay]" class="!rounded-lg h-full">
				<SwiperSlide v-for="item in categories" :key="item.id" class="relative w-full">
					<div class="p-1">
						<NuxtLink to="/" class="group flex md:flex-col-reverse flex-col items-center gap-4 rounded-xl shadow p-3 md:justify-between">
							<p class="text-center text-xs font-bold first-letter:uppercase md:text-sm">{{ item.title.uz }}</p>
							<div class="category-card-icon h-[80px] w-[80px] overflow-hidden p-0 md:mb-4 md:h-[70px] md:w-[70px] md:p-2 lg:h-[150px] lg:w-[150px]">
								<CommonImage src="" :imageClass="'!object-contain'" class="h-full w-full transition-transform duration-500 ease-in-out will-change-transform group-hover:scale-75" />
							</div>
						</NuxtLink>
					</div>
				</SwiperSlide>
			</Swiper>

			<button @click="swiperValue.slidePrev()" class="sm:block hidden absolute z-[9] left-2 shadow-md top-1/2 -translate-y-1/2 bg-white p-2 rounded-full">
				<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
					<path d="m12 19-7-7 7-7" />
					<path d="M19 12H5" />
				</svg>
			</button>

			<button @click="swiperValue.slideNext()" class="sm:block hidden absolute z-[9] right-2 shadow-md top-1/2 -translate-y-1/2 bg-white p-2 rounded-full">
				<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
					<path d="m12 5 7 7-7 7" />
					<path d="M5 12h14" />
				</svg>
			</button>
		</div>
	</div>
</template>
