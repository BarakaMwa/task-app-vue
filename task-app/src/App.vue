<template>
    <section class="header14 cid-t9Nygzys0L mbr-fullscreen mbr-parallax-background" id="header14-1">


        <div class="mbr-overlay" style="opacity: 0.3; background-color: rgb(35, 35, 35);">
        </div>

        <div class="container">
            <div class="media-container-row">

                <div class="mbr-figure" style="width: 60%;">
                    <img :src=picture :alt="firstName+' '+lastName" :title="firstName+' '+lastName"
                         :class="'img-thumbnail image-round'">
                </div>

                <div class="media-content">
                    <h1 class="mbr-section-title pb-3 align-left mbr-white mbr-fonts-style display-1">
                        <strong :class=gender >
                        {{firstName}} {{lastName}}</strong></h1>

                    <div class="mbr-section-text  pb-3 ">
                        <p class="mbr-text align-left mbr-white mbr-fonts-style display-5">
                            {{email}}</p>
                    </div>

                    <div class="media-container-column" data-form-type="formoid">
                        <div class="dragArea row form-inline">
                            <div class="col-auto buttons-wrap">
                                <button v-on:click="getNewUser()" type="submit" class="btn btn-danger display-4">Get New
                                    User
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

    export default {
        data() {
            return {
                firstName: "Baraka",
                lastName: "Mwangamba",
                gender: "male",
                email: "baraka.mwangamba@gmail.com",
                picture: "https://media-exp2.licdn.com/dms/image/C4D03AQFuW5Ptd9DcXQ/profile-displayphoto-shrink_800_800/0/1579507534250?e=1661990400&v=beta&t=fPApoMZYaHNvYUnBXBBecg4bI9PZymVSOsKoF9Wt0pQ",
            }
        },
        name: 'App',
        components: {},
        methods: {
            async getNewUser() {

                const response = await fetch('https://randomuser.me/api');

                const {results} = await response.json();

                console.log(results);

                    this.firstName = results[0].name.first,
                    this.lastName = results[0].name.last,
                    this.gender = results[0].gender,
                    this.email = results[0].email,
                    this.picture = results[0].picture.large
            }
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }

    .image-round {
        border-radius: 50%;
    }

    .male{
        background-color: blue;
        border-color: skyblue;
    }
    .female{
        background-color: blue;
        border-color: skyblue;
    }
</style>
