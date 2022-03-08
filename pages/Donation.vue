<template>
    <div id="app">
        <div id="donation" class="contain">
            <div class="overlay"></div>
        </div>
        
        <div class="c-c-cont">
            <div class="img-header">
                <img src="/prof.webp" alt="profile">
            </div>
            <div class="text-content-card">
                <h2>
                    <u>
                        Donation
                    </u>
                </h2>
                <p v-for="donate in resp[0].donation" :key="donate.id">
                    {{donate.name}} : {{donate.target}}
                </p>
                <br>
                <span>
                    {{resp[0].donation[0].uName}}
                </span>
            </div>
        </div>
    </div>
</template>

<style>
@import url(../styles/style.css);
@import url(../styles/donation.css);
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
