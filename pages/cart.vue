<template>
	<div class="mt-10">
		<h1 class="section-title">Savatcha</h1>
		<div class="grid grid-cols-1 gap-4 lg:grid-cols-[minmax(0,1fr)_400px] md:grid-cols-[minmax(0,1fr)_350px] md:gap-8">
			<div class="flex flex-col space-y-4 sm:space-y-6 py-4">
				<div class="rounded-lg dark:border shadow-md hover:shadow-lg p-4  md:p-6" v-for="key in 5" :key>
					<div class="space-y-4 md:flex md:items-center md:justify-between md:gap-4 md:space-y-0">
						<div class="shrink-0 md:order-1 h-20 w-20 md:h-28 md:w-28 border-2 rounded-xl overflow-hidden relative">
							<img class="h-full w-full object-cover" src="/assets/images/product.webp" alt="imac image" />
							<img class="hidden h-full w-full object-cover" src="/assets/images/product.webp" alt="imac image" />
						</div>

						<div class="flex items-center justify-between md:order-3 md:justify-end">
							<div class="flex items-center">
								<NumberField :default-value="1" :min="1">
									<NumberFieldContent>
										<NumberFieldDecrement />
										<NumberFieldInput class="rounded-xl" />
										<NumberFieldIncrement />
									</NumberFieldContent>
								</NumberField>
							</div>
							<div class="text-end md:order-4 md:w-32">
								<p class="text-base font-bold">560,499 so'm</p>
							</div>
						</div>

						<div class="w-full min-w-0 flex-1 md:order-2 md:max-w-md">
							<NuxtLink to="/" class="sm:text-lg text-base font-medium hover:underline mb-1">PC system All in </NuxtLink>
							<p class="text-xs text-muted-foreground mb-2">PC system All in One APPLE iMac (2023) mqrq3ro/a, Apple M3, 24" Retina 4.5K, 8GB, SSD 256GB, 10-core GPU, Keyboard layout INT</p>
							<div class="flex items-center gap-4">
								<Button variant="destructive" size="icon">
									<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-trash-2">
										<path d="M3 6h18" />
										<path d="M19 6v14c0 1-1 2-2 2H7c-1 0-2-1-2-2V6" />
										<path d="M8 6V4c0-1 1-2 2-2h4c1 0 2 1 2 2v2" />
										<line x1="10" x2="10" y1="11" y2="17" />
										<line x1="14" x2="14" y1="11" y2="17" />
									</svg>
								</Button>
							</div>
						</div>
					</div>
				</div>
			</div>
			<div class="order-last md:order-last">
				<div class="sticky top-20 rounded-xl shadow-lg dark:border bg-card p-4 text-card-foreground">
					<div class="flex flex-col gap-4">
						<h3 class="font-bold text-xl">Umumiy tavsif</h3>
						<div class="flex-center-between">Mahsulotlar <span class="font-medium">2 375 500 so'm</span></div>
						<div class="flex-center-between">Yetkazib berish <span class="font-medium">0 so'm</span></div>
						<Separator />
						<div class="flex-center-between">To'lash uchun <span class="font-medium">2 595 500 so'm</span></div>

						<Button class="rounded-xl h-10">To'lov sahifasiga o'tish</Button>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup></script>
