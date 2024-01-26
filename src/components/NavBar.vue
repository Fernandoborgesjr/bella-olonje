<script setup lang="ts">
import { RouterLink } from 'vue-router'
import Bars from '@/assets/icons/Bars.vue'
import { Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'

const navigation = [
  { name: 'Home', href: '/' },
  { name: 'About', href: '/about' },
  { name: 'Faq', href: '/about' },
  { name: 'Contact', href: '/about' }
]
</script>

<template>
  <nav class="flex gap-6 justify-between">
    <i>icone</i>
    <div>
      <Menu as="div" class="relative inline-block md:hidden">
        <MenuButton>
          <Bars class="md:hidden cursor-pointer text-gray-500" />
        </MenuButton>

        <transition
          enter-active-class="transition ease-out duration-100"
          enter-from-class="transform opacity-0 scale-95"
          enter-to-class="transform opacity-100 scale-100"
          leave-active-class="transition ease-in duration-75"
          leave-from-class="transform opacity-100 scale-100"
          leave-to-class="transform opacity-0 scale-95"
        >
          <MenuItems
            class="absolute right-0 z-10 mt-2 w-48 origin-top-right rounded-md bg-white py-1 shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none"
          >
            <MenuItem v-for="link in navigation" :key="link.href" v-slot="{ active }">
              <RouterLink
                :class="[active ? 'bg-gray-100' : '', 'block px-4 py-2 text-sm text-gray-700']"
                :to="link.href"
                >{{ link.name }}</RouterLink
              >
            </MenuItem>
          </MenuItems>
        </transition>
      </Menu>
      <ul class="flex gap-x-6 gap-y-2"></ul>
    </div>
  </nav>
</template>
