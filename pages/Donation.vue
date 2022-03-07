<template>
    <div id="donation" class="contain">

    </div>
</template>

<style>
@import url(../styles/style.css);
@import url(../styles/animate.css);
@import url(../styles/mobile.css);
@import url('https://fonts.googleapis.com/css2?family=IBM+Plex+Sans+Thai:wght@300&display=swap');
</style>

<script setup>
    useMeta({
    title: 'Donation | detzz.in.th',
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
