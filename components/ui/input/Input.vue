<script setup lang="ts">
import type { HTMLAttributes } from 'vue'
import { cn } from '@/lib/utils'
import { useVModel } from '@vueuse/core'

const props = defineProps<{
	defaultValue?: string | number
	modelValue?: string | number
	error?: boolean
	class?: HTMLAttributes['class']
}>()

const emits = defineEmits<{
	(e: 'update:modelValue', payload: string | number): void
}>()

const modelValue = useVModel(props, 'modelValue', emits, {
	passive: true,
	defaultValue: props.defaultValue
})
</script>

<template>
	<input
		v-model="modelValue"
		:class="
			cn(
				'flex h-9 w-full rounded-md border border-input bg-transparent px-3 py-1 text-sm transition-colors file:border-0 file:bg-transparent file:text-sm file:font-medium placeholder:text-muted-foreground focus-visible:outline-none focus:border-primary focus:outline-none disabled:cursor-not-allowed disabled:opacity-50',
				props.class,
				{ '!border-destructive': props.error }
			)
		"
	/>
</template>
