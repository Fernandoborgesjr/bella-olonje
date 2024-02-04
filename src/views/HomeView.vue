<script setup lang="ts">
import CallToActionButton from '@/components/CallToActionButton.vue'
import { type ImgHTMLAttributes } from 'vue'

type Section = {
  title: string
  subtitle: string
  description: string
  image: ImgHTMLAttributes
}

const sections: Section[] = [
  {
    title: 'Create an account',
    subtitle: 'Create/login to an existing account to get started',
    description: 'An account is created with your email and a desired password',
    image: {
      src: new URL('@/assets/img/signup-mockup.webp', import.meta.url).href,
      alt: 'Create account screen on app',
      width: '600px',
      height: '758px',
      loading: 'lazy'
    }
  },
  {
    title: 'Explore while shopping',
    subtitle: 'Shop for your favorites meal as e dey hot.',
    description:
      'Shop for your favorite meals or drinks and enjoy while doing it.',
    image: {
      src: new URL('@/assets/img/home-mockup.webp', import.meta.url).href,
      alt: 'Home screen on app',
      width: '600px',
      height: '758px',
      loading: 'lazy'
    }
  },
  {
    title: 'Checkout',
    subtitle: 'When you done check out and get it delivered.',
    description: 'When you done check out and get it delivered with ease.',
    image: {
      src: new URL('@/assets/img/checkout-mockup.webp', import.meta.url).href,
      alt: 'Checkout screen on app',
      width: '600px',
      height: '758px',
      loading: 'lazy'
    }
  }
]

;(function addPreloadImage() {
  if (document.getElementById('preload_home_image')) return

  const preload: HTMLLinkElement = document.createElement('link')
  preload.id = 'preload_home_image'
  preload.rel = 'preload'
  // preload.fetchPriority = 'high' // TODO: enable when more browsers are supported
  preload.as = 'image'
  preload.href = new URL('@/assets/img/app-mockup.webp', import.meta.url).href
  preload.type = 'image/webp'

  document.head.appendChild(preload)
})()
</script>

<template>
  <main class="bg-gray-50">
    <section
      class="container mx-auto px-4 py-12 flex flex-col items-center gap-10 text-center"
    >
      <div class="flex flex-col gap-6">
        <h1 class="text-base font-semibold text-gray-600">Food app</h1>
        <p class="text-4xl font-bold text-[#252B42]">
          Why stay hungry when you can order form Bella Olonje
        </p>
        <p class="text-2xl text-gray-600">
          Download the bella olonje&#8217;s food app now on
        </p>
      </div>
      <div class="flex flex-col gap-4">
        <CallToActionButton
          as="a"
          href="#"
          class="bg-[#FA4A0C] text-white w-60"
          pill
        >
          Playstore
        </CallToActionButton>
        <CallToActionButton
          as="a"
          href="#"
          class="bg-[#FA4A0C] text-white w-60"
          pill
        >
          App store
        </CallToActionButton>
      </div>
    </section>

    <section class="container mx-auto px-4 flex flex-col items-center gap-2">
      <img
        src="@/assets/img/app-mockup.webp"
        alt="food app"
        width="680"
        height="777"
      />
      <div class="flex flex-col w-full gap-8">
        <h2
          class="md:order-2 text-[#252B42] text-2xl self-center font-semibold"
        >
          How the app works
        </h2>
        <hr class="order-2 md:order-1 border-2" />
      </div>
    </section>

    <section
      v-for="{ title, subtitle, description, image } in sections"
      :key="title"
      class="container mx-auto pt-8 px-4 flex flex-col text-center gap-[30px] items-center"
    >
      <img v-bind="image" class="order-2" />
      <div class="order-1 md:order-2 flex flex-col gap-[30px]">
        <h2 class="text-[#FA4A0C] font-bold text-2xl">{{ title }}</h2>
        <p class="font-bold text-[40px]/[57px] text-[#252B42]">
          {{ subtitle }}
        </p>
        <p class="font-medium text-2xl text-gray-500 px-16">
          {{ description }}
        </p>
      </div>
    </section>

    <section
      class="container mx-auto px-4 py-20 flex flex-col items-center gap-10 text-center bg-[#252B42]"
    >
      <div class="flex flex-col gap-6">
        <h2 class="text-4xl font-bold text-white">Download the app now.</h2>
        <p class="text-2xl font-medium text-gray-400">
          Most calendars are designed for teams.
        </p>
      </div>
      <div class="flex gap-4 box-border">
        <CallToActionButton
          as="a"
          href="#"
          class="bg-[#FA4A0C] text-white box-border"
        >
          Buy now
        </CallToActionButton>
        <CallToActionButton
          as="a"
          href="#"
          class="text-white box-border"
          outlined
        >
          Try for free
        </CallToActionButton>
      </div>
    </section>
  </main>
</template>
