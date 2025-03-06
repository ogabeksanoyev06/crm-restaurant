<template>
	<div class="hidden xl:block">
		<div class="sticky top-16 h-[calc(100vh-4rem)]">
			<div class="h-full border border-dashed rounded-t-xl overflow-hidden">
				<div class="flex flex-col h-full">
					<p class="text-lg font-semibold p-4">Savat</p>
					<div class="no-scrollbar h-full overflow-y-auto">
						<!-- <CommonNoData :text="'Hozircha savatingiz boʻsh'" /> -->
						<NuxtLink to="/" class="flex-center-between gap-2 py-2 px-4 hover:bg-muted-foreground/10 transition-300" v-for="i in 5" :key="i">
							<div class="flex-y-center gap-2">
								<div class="relative overflow-hidden shrink-0 w-10 h-10 flex-center">
									<CommonImage alt="avatar-image" class="object-cover w-full h-full" src="https://cdn.commeta.uz/60x/https://cdn.commeta.uz/media/uploaded/2023/12/21/commeta_Btqc6dL.png" />
								</div>
								<div class="flex flex-col gap-0.5">
									<h5 class="font-medium text-sm line-clamp-1">
										Samarqand zigi'r oshini tatib ko'ring! O'zgacha to'g'ralgan go‘sht, xushbo‘y ziravorlar va zig'ir yog'i o'ziga xos ta'mga ega nafis taom yaratadi. Hoziroq buyurtma bering va Samarqandning haqiqiy kulinariya asaridan bahramand
										bo'ling!
									</h5>
									<p class="text-xs line-clamp-1 text-muted-foreground font-medium">33,000 so'm</p>
								</div>
							</div>
							<button class="flex-center gap-1 w-10 h-10 opacity-55 hover:opacity-100">
								<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="w-5 h-5">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M9.75 3.5C9.33579 3.5 9 3.83579 9 4.25V5H15V4.25C15 3.83579 14.6642 3.5 14.25 3.5H9.75ZM7.5 4.25V5H3.75C3.33579 5 3 5.33579 3 5.75C3 6.16421 3.33579 6.5 3.75 6.5H4.30005L5.62088 19.9681C5.73386 21.1202 6.70255 21.9985 7.86014 21.9985H16.1399C17.2975 21.9985 18.2661 21.1202 18.3791 19.9681L19.7 6.5H20.25C20.6642 6.5 21 6.16421 21 5.75C21 5.33579 20.6642 5 20.25 5H16.5V4.25C16.5 3.00736 15.4926 2 14.25 2H9.75C8.50736 2 7.5 3.00736 7.5 4.25ZM11 9.75C11 9.33579 10.6642 9 10.25 9C9.83579 9 9.5 9.33579 9.5 9.75V17.25C9.5 17.6642 9.83579 18 10.25 18C10.6642 18 11 17.6642 11 17.25V9.75ZM14.5 9.75C14.5 9.33579 14.1642 9 13.75 9C13.3358 9 13 9.33579 13 9.75V17.25C13 17.6642 13.3358 18 13.75 18C14.1642 18 14.5 17.6642 14.5 17.25V9.75Z"
										fill="black"
									></path>
								</svg>
							</button>
						</NuxtLink>
					</div>
					<div class="p-4 grid gap-2">
						<div class="flex items-center justify-between">
							<div class="flex-center gap-2">
								<div class="flex-shrink-0 w-10 h-10 flex-center bg-secondary rounded-xl">
									<img src="/assets/icons/avatars.svg" alt="" />
								</div>
								<span>Yetkazib berish 0 soʻm</span>
							</div>
							<button>
								<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="w-5 h-5">
									<circle cx="12" cy="12" r="10" />
									<path d="M12 16v-4" />
									<path d="M12 8h.01" />
								</svg>
							</button>
						</div>
						<Button class="w-full justify-between h-12 rounded-lg">
							<span>Umumiy narx</span>
							<span class="text-lg font-semibold">129,000 so'm</span>
						</Button>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup></script>
