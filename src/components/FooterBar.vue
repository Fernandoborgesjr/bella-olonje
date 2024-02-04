<script setup lang="ts">
import type { ImgHTMLAttributes } from 'vue'
type SocialMedia = {
  link: string
  image: ImgHTMLAttributes
}

const socialMedias: SocialMedia[] = [
  {
    link: 'https://twitter.com/',
    image: {
      src: new URL(
        '@/assets/icons/ant-design_twitter-outlined.svg',
        import.meta.url
      ).href,
      alt: 'twitter',
      width: 41,
      height: 41
    }
  },
  {
    link: 'https://www.linkedin.com/in/fernando-borges-a84059ab',
    image: {
      src: new URL(
        '@/assets/icons/ant-design_linkedin-filled.svg',
        import.meta.url
      ).href,
      alt: 'twitter',
      width: 41,
      height: 41
    }
  },
  {
    link: 'https://www.facebook.com/',
    image: {
      src: new URL(
        '@/assets/icons/ant-design_facebook-filled.svg',
        import.meta.url
      ).href,
      alt: 'twitter',
      width: 41,
      height: 41
    }
  }
]
</script>

<template>
  <footer class="container mx-auto p-10 justify-self-end">
    <div class="flex flex-col items-center gap-2">
      <div class="flex gap-6 justify-center">
        <template v-for="{ image, link } in socialMedias" :key="link">
          <a :href="link" target="_blank">
            <img
              :src="image.src"
              :alt="image.alt"
              :width="image.width"
              :height="image.height"
              loading="lazy"
            />
          </a>
        </template>
      </div>
      <p class="text-xs font-semibold text-gray-600">
        Just type what's on your mind and we'll
      </p>
    </div>
  </footer>
</template>
