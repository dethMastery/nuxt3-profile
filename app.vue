<template>
    <div id="app">
        <!-- Header -->
        <div id="heading" class="contain">
            <div class="overlay">
                <div class="text-container">
                    <!-- <h1>
                        Suphakit Pinyoworapot
                    </h1>-->
                    <h1>
                        {{ resp[0].name }} {{ resp[0].sName }}
                    </h1>
                    <h3>
                        {{ resp[0].quote }}
                    </h3>
                </div>
            </div>
        </div>

        <!-- About -->
        <div id="about" class="contain">
            <h2 class="heading">
                <span>
                    About Me
                </span>
            </h2>
        </div>
    </div>
</template>

<style>
@import url(https://unpkg.com/aos@next/dist/aos.css);
@import url(./styles/style.css);
@import url(./styles/animate.css);
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Thai:wght@300&display=swap');
</style>

<script setup>
useMeta({
  title: 'Suphakit P. | detzz.in.th',
  meta: [
      {
          name: 'viewport',
          content: 'width=device-width, initial-scale=1, maximum-scale=1',
      }
  ]
});

let api = "https://api.detzz.in.th/profile";
let {data: resp} = await useFetch(api);

</script>