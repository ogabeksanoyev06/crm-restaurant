<script setup>
const token = useCookie('access');
const open = ref(false);
</script>

<template>
	<Button class="h-8 w-8 max-lg:p-0 lg:w-auto" v-if="!token" @click="open = true">
		<span class="hidden lg:inline-flex">Kirish</span>
		<span class="inline-flex lg:hidden">
			<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-log-in">
				<path d="M15 3h4a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2h-4" />
				<polyline points="10 17 15 12 10 7" />
				<line x1="15" x2="3" y1="12" y2="12" />
			</svg>
		</span>
	</Button>
	<ModalAuth v-model="open" />
	<DropdownMenu v-if="token">
		<DropdownMenuTrigger as-child>
			<Avatar class="cursor-pointer w-8 h-8">
				<AvatarImage src="https://github.com/unovue.png" alt="@unovue" />
			</Avatar>
		</DropdownMenuTrigger>
		<DropdownMenuContent class="w-64 mb-6">
			<div class="px-2 py-1.5 text-sm font-semibold">
				<div class="relative mb-2 flex flex-col items-center justify-center gap-y-3 rounded-md bg-muted pb-5 pt-7">
					<Avatar>
						<AvatarImage src="https://github.com/unovue.png" alt="@unovue" />
						<AvatarFallback>CN</AvatarFallback>
					</Avatar>
					<div class="flex flex-col items-center justify-center"><span class="text-sm font-medium">+998930819140</span><span class="text-xs text-muted-foreground"> Sanoyev Og'abek Otabek o'g'li</span></div>
				</div>
			</div>
			<NuxtLink to="/profile">
				<DropdownMenuItem class="flex cursor-pointer items-center gap-x-2">
					<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="iconify iconify--ph" font-size="16" width="1em" height="1em" viewBox="0 0 256 256">
						<g fill="currentColor">
							<path d="M192 96a64 64 0 1 1-64-64a64 64 0 0 1 64 64" opacity=".2"></path>
							<path
								d="M230.92 212c-15.23-26.33-38.7-45.21-66.09-54.16a72 72 0 1 0-73.66 0c-27.39 8.94-50.86 27.82-66.09 54.16a8 8 0 1 0 13.85 8c18.84-32.56 52.14-52 89.07-52s70.23 19.44 89.07 52a8 8 0 1 0 13.85-8M72 96a56 56 0 1 1 56 56a56.06 56.06 0 0 1-56-56"
							></path>
						</g>
					</svg>
					<span>Shaxsiy</span>
				</DropdownMenuItem>
			</NuxtLink>
			<NuxtLink to="/payments">
				<DropdownMenuItem class="flex cursor-pointer items-center gap-x-2">
					<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="iconify iconify--lucide" font-size="16" width="1em" height="1em" viewBox="0 0 24 24">
						<g fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2">
							<rect width="20" height="14" x="2" y="5" rx="2"></rect>
							<path d="M2 10h20"></path>
						</g>
					</svg>
					<span>To'lovlar</span>
				</DropdownMenuItem>
			</NuxtLink>
			<NuxtLink to="/">
				<DropdownMenuItem class="flex cursor-pointer items-center gap-x-2">
					<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="iconify iconify--iconamoon" font-size="16" width="1em" height="1em" viewBox="0 0 24 24">
						<g fill="none">
							<path
								fill="currentColor"
								fill-rule="evenodd"
								d="M3.4 9.345a9 9 0 0 1 2-3.466l1.6.925c1.333.77 3-.193 3-1.732v-1.85a9 9 0 0 1 4 .003v1.847c0 1.54 1.667 2.502 3 1.732l1.601-.925a9 9 0 0 1 2 3.465L19 10.268c-1.333.77-1.333 2.694 0 3.464l1.6.923a9 9 0 0 1-1.998 3.466L17 17.196c-1.333-.77-3 .193-3 1.732v1.85a9 9 0 0 1-4-.003v-1.847c0-1.54-1.667-2.502-3-1.732l-1.601.925a9 9 0 0 1-2-3.465l1.6-.924c1.334-.77 1.334-2.694 0-3.464zM12 14a2 2 0 1 0 0-4a2 2 0 0 0 0 4"
								clip-rule="evenodd"
								opacity=".16"
							></path>
							<circle cx="12" cy="12" r="2" stroke="currentColor" stroke-width="2"></circle>
							<path
								fill="currentColor"
								d="m5.399 5.88l.5-.867a1 1 0 0 0-1.234.186zM3.4 9.344l-.956-.295a1 1 0 0 0 .456 1.16zm-.002 5.311l-.5-.866a1 1 0 0 0-.455 1.162zm2 3.464l-.734.68a1 1 0 0 0 1.234.187zm4.6 2.655H9a1 1 0 0 0 .778.975zm4.001.002l.223.975a1 1 0 0 0 .777-.975zM18.6 18.12l-.5.866a1 1 0 0 0 1.233-.186zm1.998-3.466l.956.295a1 1 0 0 0-.456-1.16zm.002-5.311l.5.866a1 1 0 0 0 .455-1.162zm-2-3.465l.734-.679a1 1 0 0 0-1.234-.187zM14 3.225h1a1 1 0 0 0-.777-.975zm-4-.002l-.223-.975A1 1 0 0 0 9 3.223zm4 1.849h-1zm5 8.66l-.5.866zm-2 3.464l-.5.866zM5 13.732l.5.866zm2-6.928l-.5.866zM4.356 9.639a8 8 0 0 1 1.776-3.08L4.665 5.2a10 10 0 0 0-2.22 3.85zM5.072 16a8 8 0 0 1-.718-1.64l-1.91.592c.217.701.515 1.388.896 2.048zm1.06 1.441A8 8 0 0 1 5.073 16L3.34 17c.38.66.827 1.261 1.325 1.8zm7.646 2.361a8 8 0 0 1-3.556-.002l-.445 1.95a10 10 0 0 0 4.446.002zm5.866-5.441a8 8 0 0 1-1.776 3.08l1.467 1.36a10 10 0 0 0 2.22-3.85zM18.928 8c.306.53.545 1.08.718 1.64l1.91-.592A10 10 0 0 0 20.66 7zm-1.06-1.441c.397.43.754.91 1.06 1.441l1.732-1a10 10 0 0 0-1.325-1.8zm-7.646-2.361a8 8 0 0 1 3.556.002l.444-1.95a10 10 0 0 0-4.445-.002zm.778.874v-1.85H9v1.85zm-3.5.866l-1.601-.925l-1 1.732l1.6.925zm-3 6.928l-1.601.924l1 1.732l1.6-.924zm1-3.464l-1.6-.923l-1 1.732l1.6.923zM11 20.775v-1.847H9v1.847zM6.5 16.33l-1.601.925l1 1.732l1.6-.925zm12.601.925L17.5 16.33l-1 1.732l1.601.925zM15 20.777v-1.849h-2v1.85zm5.101-12.3l-1.601.925l1 1.732l1.601-.924zm.998 5.312l-1.599-.923l-1 1.732l1.6.923zM15 5.072V3.225h-2v1.847zm3.101-.059l-1.601.925l1 1.732l1.601-.925zM13 5.072c0 2.31 2.5 3.753 4.5 2.598l-1-1.732a1 1 0 0 1-1.5-.866zm5.5 4.33c-2 1.155-2 4.041 0 5.196l1-1.732a1 1 0 0 1 0-1.732zm-1 6.928c-2-1.154-4.5.289-4.5 2.598h2a1 1 0 0 1 1.5-.866zM11 18.928c0-2.31-2.5-3.753-4.5-2.598l1 1.732a1 1 0 0 1 1.5.866zm-5.5-4.33c2-1.155 2-4.041 0-5.196l-1 1.732a1 1 0 0 1 0 1.732zM9 5.072a1 1 0 0 1-1.5.866l-1 1.732c2 1.155 4.5-.289 4.5-2.598z"
							></path>
						</g>
					</svg>
					<span>Sozlamalar</span>
				</DropdownMenuItem>
			</NuxtLink>
			<NuxtLink to="/">
				<DropdownMenuItem class="flex cursor-pointer items-center gap-x-2">
					<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="iconify iconify--iconamoon" font-size="16" width="1em" height="1em" viewBox="0 0 24 24">
						<g fill="none">
							<circle cx="12" cy="12" r="9" fill="currentColor" opacity=".16"></circle>
							<circle cx="12" cy="12" r="9" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2"></circle>
							<path stroke="currentColor" stroke-linejoin="round" stroke-width="3" d="M12 16h.01v.01H12z"></path>
							<path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.586 7.586c.39-.39.9-.585 1.41-.586a2 2 0 0 1 1.418.586c.39.39.586.902.586 1.414s-.195 1.024-.586 1.414a2 2 0 0 1-1.418.586L12 12"></path>
						</g>
					</svg>
					<span>Yordam</span>
				</DropdownMenuItem>
			</NuxtLink>
			<DropdownMenuSeparator />
			<DropdownMenuItem class="flex cursor-pointer items-center gap-x-2">
				<svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" aria-hidden="true" role="img" class="iconify iconify--lets-icons" font-size="16" width="1em" height="1em" viewBox="0 0 24 24">
					<defs>
						<mask id="iconifyReact51">
							<g fill="none">
								<circle cx="6" cy="6" r="6" fill="#fff" fill-opacity=".25" transform="matrix(0 -1 -1 0 20 18)"></circle>
								<path stroke="silver" stroke-opacity=".25" stroke-width=".6" d="M7.7 12a6.3 6.3 0 1 1 12.6 0a6.3 6.3 0 0 1-12.6 0Z"></path>
								<path stroke="#fff" stroke-width="1.2" d="M8 18.928A8 8 0 1 0 8 5.072"></path>
								<path fill="#fff" d="m2 12l-.469-.375l-.3.375l.3.375zm9 .6a.6.6 0 1 0 0-1.2zM5.531 6.625l-4 5l.938.75l4-5zm-4 5.75l4 5l.938-.75l-4-5zM2 12.6h9v-1.2H2z"></path>
							</g>
						</mask>
					</defs>
					<path fill="currentColor" d="M0 0h24v24H0z" mask="url(#iconifyReact51)"></path>
				</svg>
				<span>Chiqish</span>
			</DropdownMenuItem>
		</DropdownMenuContent>
	</DropdownMenu>
</template>
