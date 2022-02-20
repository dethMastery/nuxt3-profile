<template>
    <div id="app">
        hello
    </div>
</template>

<style>
@import url(https://unpkg.com/aos@next/dist/aos.css);
@import url(./styles/style.css);
</style>

<script setup>
import AOS from 'aos';

AOS.init();

useMeta({
  title: 'Suphakit P. | detzz.in.th',
  meta: [
      {
          name: 'viewport',
          content: 'width=device-width, initial-scale=1, maximum-scale=1',
      }
  ]
});
</script>