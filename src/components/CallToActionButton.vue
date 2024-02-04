<script setup lang="ts">
type Props = {
  variant?: 'a' | 'b'
  label?: string
  as?: 'button' | 'a'
  pill?: boolean
  outlined?: boolean
}

const props = withDefaults(defineProps<Props>(), {
  variant: 'a',
  as: 'button',
  pill: false,
  outlined: false
})

const style = [
  'p-5 font-bold shadow-lg text-xl',
  props.pill ? 'rounded-[30px]' : 'rounded-[10px]',
  'hover:scale-105 hover:shadow-slate-300',
  { border: props.outlined }
]
</script>

<template>
  <button v-if="'button' === as" :class="style" v-bind="$attrs">
    <slot>{{ label }}</slot>
  </button>
  <a v-if="'a' === as" :class="style" v-bind="$attrs">
    <slot>{{ label }}</slot>
  </a>
</template>
