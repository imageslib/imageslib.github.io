<script setup lang="ts">
// if(typeof location !== 'undefined'){
//   location.replace('https://www.tobetter.org.cn')
// }

const imgs = import.meta.glob(
    [
      '/public/img/**/*.png',
      '/public/img/**/*.svg',
      '/public/img/**/*.jpeg',
      '/public/img/**/*.jpg',
    ],
    {
      eager: true,
      as: 'url'// https://vitejs.cn/vite3-cn/guide/features.html#glob-import
    })
</script>

<template>
  <div>
    <fieldset
      v-for="(img,idx) in imgs"
     :key="img"
      style="margin-bottom: 20px; padding: 20px"
    >
      <legend v-if="img.indexOf('data:image/')!==-1">
        {{img.replace('/public', 'https://imageslib.github.io')}}
      </legend>
      <img :src="img"/>
    </fieldset>
  </div>
</template>

<style scoped>
</style>
