<template>
    <div class="header media">
        <img class="align-self-start mr-3 d-none d-sm-block" src="../static/photo/photo.jpg" alt="Generic placeholder image">
        <div class="media-body">
            <h5 class="mt-0">{{ name }}</h5>
            <h4>{{ poste }}</h4>
            <p>
                <icon name="map-marker"></icon> {{ city }}
            </p>
            <p class="media-info">
                <span v-if="email"><a :href="'mailto:'+ email"><icon class="social" name="envelope" scale="2"></icon></a></span>
                <span v-if="social.github"><a title="GitHub" :href="'//github.com/'+ social.github" target="_blank"><icon class="social" name="brands/github-square" scale="2"></icon></a></span>
                <span v-if="social.linkedin"><a title="LinkedIn" :href="'//linkedin.com/in/'+ social.linkedin" target="_blank"><icon class="social" name="brands/linkedin" scale="2"></icon></a></span>
                <span v-if="social.twitter"><a title="Twitter" :href="'//twitter.com/'+ social.twitter" target="_blank"><icon class="social" name="brands/twitter-square" scale="2"></icon></a></span>
                <!--<span><a :href="'//twitter.com/'+ social.twitter" target="_blank"><icon class="social" name="print" scale="2"></icon> test</a></span>-->
            </p>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Header",
        props: ["name","poste","city","email","social"],
        data(){
            return {
                cv_label: "CV",
                cv_icon: "print"
            }
        }
    }
</script>

<style scoped>
    .header {
        background-color: #f0f0f0;
        border-bottom: 1px solid #dddddd;
        box-shadow: 0 0 3px rgba(190, 190, 190, 0.75);
        top: 0;
        right: 0;
        left: 0;
        z-index: 1030;
        height: auto;
        padding: 20px 0;
        margin-bottom: 20px;
        margin-left: 10px;
    }

    .header img {
        width: 150px;
    }

    .header li {
        list-style-type: none;
        padding: 4px 0;
    }

    .header ul {
        margin-top: 5px;
        margin-left: 0;
        padding-left: 0;
    }
    .header h5 {
        color: rgb(186, 78, 78);
        font-size: 2em;
    }

    .media-info span {
        margin: 0 5px 0 0;
    }

    .media-info span a {
        color: #337ab7;
    }

    .social:hover {
        -webkit-transform: scale(1.1);
        -moz-transform: scale(1.1);
        -o-transform: scale(1.1);
    }
    .social {
        -webkit-transform: scale(0.8);
        /* Browser Variations: */

        -moz-transform: scale(0.8);
        -o-transform: scale(0.8);
        -webkit-transition-duration: 0.5s;
        -moz-transition-duration: 0.5s;
        -o-transition-duration: 0.5s;
    }

    /*
        Multicoloured Hover Variations
    */

    #social-fb:hover {
        color: #3B5998;
    }
    #social-tw:hover {
        color: #4099FF;
    }
    #social-gp:hover {
        color: #d34836;
    }
    #social-em:hover {
        color: #f39c12;
    }
</style>