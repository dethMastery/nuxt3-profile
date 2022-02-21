<template>
    <div id="app">
        <!-- Header -->
        <div id="heading" class="contain">
            <div class="overlay">
                <div class="text-cont">
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
                <div>
                    <b>
                        About Me
                    </b>
                </div>
            </h2>

            <div class="ab-cont">
                <div class="left">
                    <div class="img-cont">
                        <img :src="resp[0].proPic" alt="Profile Picture">
                    </div>
                </div>

                <div class="right">
                    <div class="text-cont">
                        <div class="desc">
                            <h1>
                                {{resp[0].desc}}
                            </h1>
                            <p>
                                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{{resp[0].subDesc}}
                            </p>
                        </div>
                        <br>
                        <div class="basic-info">
                            <h2>
                                <u>Basic Info</u> >
                            </h2>
                            <ul>
                                <li>
                                    <b>Name</b> : {{resp[0].name}} {{resp[0].sName}}                            
                                </li>
                                <li>
                                    <b>Age</b> : {{age}}
                                </li>
                                <li>
                                    <b>Education Profile</b> : 
                                    <ul>
                                        <li v-for="edu in resp[0].Education.reverse()" :key="edu.id">
                                            {{ edu.grade }} :  {{ edu.class }} {{ edu.school }} [{{edu.year}}]
                                        </li>
                                    </ul>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
@import url(https://unpkg.com/aos@next/dist/aos.css);
@import url(./styles/style.css);
@import url(./styles/animate.css);
@import url(./styles/mobile.css);
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

let bday = 1024074000000;

let today = new Date().getFullYear();
let birth = new Date(bday).getFullYear();
let age = today - birth;


</script>