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
            <h1 class="heading">
                <div>
                    <b>
                        About Me
                    </b>
                </div>
            </h1>

            <div class="ab-cont">
                <div class="left">
                    <div class="img-cont">
                        <span>
                            <img :src="resp[0].proPic" alt="Profile Picture">
                        </span>
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
                                <li class="eduProf">
                                    <b>Education Profile</b> : 
                                    <ul>
                                        <li v-for="edu in resp[0].Education.reverse()" :key="edu.id">
                                            {{ edu.school }} [{{edu.year}}]
                                        </li>
                                    </ul>
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Skill -->
        <div id="skill" class="contain">
            <h1 class="heading">
                <div>
                    My Skills
                </div>
            </h1>

            <div class="c-cont">
                <div class="card" v-for="skl in resp[0].skill" :key="skl.id">
                    <div class="imghol">
                        <img :src="skl.path" alt="img">
                    </div>
                    <div class="container">
                        <h3><b>{{skl.name}}</b></h3>
                        <p>{{skl.duration}}</p>
                    </div>
                </div>                
            </div>
        </div>

        <!-- Work Status-->
        <div id="work" class="contain">
            <h1 class="heading">
                <div>
                    My Worked Repository
                </div>
            </h1>

            <div class="feature">
                <h3>
                    Featured Repository :
                </h3>
                <br>
                <div class="c-cont">
                    <div v-for="repp in resp[0].fRepo" :key="repp.id" class="card">
                        <div class="card-header">
                            {{repp.name}}
                        </div>
                        <div class="card-body">
                            {{repp.desp}}
                        </div>
                        <div class="card-footer">
                            {{repp.lang}} &middot; <a :href="repp.link" class="button">Repo Link ></a>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Work History -->
        <div id="history" class="contain">
            <h1 class="heading">
                <div>
                    Work experience
                </div>
            </h1>
            <div class="c-cont">
                <div class="card" v-for="wxp in resp[0].Work" :key="wxp.id">
                    <div class="bg" :style="'background: url('+wxp.img+')'">
                        <div class="overlay">
                            <div class="img">
                                <img :src="wxp.img" alt="logo">
                            </div>
                            <div class="text">
                                <h3>
                                    {{wxp.class}} @ {{wxp.name}}
                                </h3>

                                <p class="sub">
                                    {{wxp.duration}}
                                </p>

                                <h2>
                                    Status : 
                                    <span v-if="wxp.status == 1">
                                        Working
                                    </span>
                                    <span v-else-if="wxp.status == 0">
                                        Fired
                                    </span>
                                </h2>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Certifcate -->
        <div id="cert" class="contain">
            <h1 class="heading">
                <div>
                    Certificate
                </div>
            </h1>

            <div class="c-cont">
                <div v-for="cert in resp[0].cert " :key="cert.id">
                    <div v-if="cert.name != null">
                        sry boi im lazy now~
                    </div>
                    <div v-else>
                        nothing to show here now..
                    </div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <div id="footer">
            <div class="cont">
                <div class="about">
                    <ul>
                        <li>Address :</li>
                        <li v-for="add in resp[0].footer[0].Address" :key="add.id" class="address">
                            {{add.content}}
                        </li>
                        <li>
                            &nbsp;
                        </li>
                        <a :href="'tel:' + resp[0].footer[0].Tel">
                            <li>
                                tel: {{resp[0].footer[0].shTel}}
                            </li>
                        </a>
                        <a :href="'mailto:' + resp[0].footer[0].mail">
                            <li>
                                e-mail: {{resp[0].footer[0].mail}}
                            </li>
                        </a>
                    </ul>
                </div>
                <div class="menu">
                    <ul>
                        <li>
                            Menu :
                        </li>
                        <a v-for="menu in resp[0].footer[0].menu" :key="menu.id" :href="menu.link">
                            <li class="menu">
                                {{menu.name}}
                            </li>
                        </a>
                    </ul>
                </div>
                <div class="link">
                    <ul>
                        <li>
                            Social :
                        </li>
                        <a v-for="social in resp[0].footer[0].social" :key="social.id" :href="social.link">
                            <li class="social">
                                <i :class="social.icon"></i> {{social.text}}
                            </li>
                        </a>
                    </ul>
                </div>
            </div>
        </div>
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