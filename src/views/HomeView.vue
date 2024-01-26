<script setup lang="ts">
const sections = [
  {
    title: 'Create an account',
    subtitle: 'Create/login to an existing account to get started',
    description: 'An account is created with your email and a desired password',
    image: {
      src: new URL('@/assets/img/signup-mockup.png', import.meta.url).href,
      alt: 'Create account screen on app'
    }
  },
  {
    title: 'Explore while shopping',
    subtitle: 'Shop for your favorites meal as e dey hot.',
    description:
      'Shop for your favorite meals or drinks and enjoy while doing it.',
    image: { src: '', alt: '' }
  },
  {
    title: 'Checkout',
    subtitle: 'When you done check out and get it delivered.',
    description: 'When you done check out and get it delivered with ease.',
    image: { src: '', alt: '' }
  }
]
</script>

<template>
  <main class="container mx-auto bg-gray-100">
    <section>
      <h1>Food app</h1>
      <p>Why stay hungry when you can order form Bella Onojie</p>
      <p>Download the bella onoje&#8217;s food app now on</p>
      <div>
        <button>Playstore</button>
        <button>App store</button>
      </div>
    </section>
    <section>
      <img src="" alt="food app" />
      <div class="flex flex-col">
        <h2 class="md:order-2">How the app works</h2>
        <hr class="order-2 md:order-1" />
      </div>
    </section>

    <section
      v-for="{ title, subtitle, description, image } in sections"
      :key="title"
      class="flex flex-col text-center gap-[30px] items-center"
    >
      <img :src="image.src" :alt="image.alt" class="order-2" />
      <div class="order-1 md:order-2 flex flex-col gap-[30px]">
        <h2 class="text-[#FA4A0C] font-bold text-2xl">{{ title }}</h2>
        <p class="font-bold text-[40px]/[57px] text-[#252B42]">
          {{ subtitle }}
        </p>
        <p>{{ description }}</p>
      </div>
    </section>
  </main>
</template>
