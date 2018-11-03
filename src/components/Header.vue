<template>
    <div class="header media">
        <div class="container-fluid">
            <div class="row">
                <div class="col-12 col-sm-10">
                    <img class="align-self-start mr-3 d-none d-sm-block" src="../static/photo/photo.jpg" alt="Generic placeholder image">
                    <div class="media-body">
                        <h5 class="mt-0">{{ name }}</h5>
                        <h4>{{ poste }}</h4>
                        <div class="coordonnees">
                            <span><icon name="map-marker"></icon> {{ city }}</span>
                            <span class="break" />
                            <span v-if="email"><icon name="envelope" scale="1.2"></icon><a :href="'mailto:'+ email">{{ email }}</a></span>
                            <span v-if="social.github"><icon name="brands/github-square" scale="1.2"></icon><a title="GitHub" :href="'//github.com/'+ social.github" target="_blank">@{{ social.github }}</a></span>
                            <span v-if="social.linkedin"><icon name="brands/linkedin" scale="1.2"></icon><a title="LinkedIn" :href="'//linkedin.com/in/'+ social.linkedin" target="_blank">beckf</a></span>
                            <span class="break" />
                            <span v-if="other" class="saut">{{ other }}</span>
                        </div>
                    </div>
                </div>
                <div class="col-sm-2 d-none d-sm-block align-self-end download-buttons">
                    <a v-if="cv_pdf" :href="cv_pdf" type="button" class="btn btn-primary btn-sm">
                        <icon :name="cv_icon"></icon> {{ cv_label }}
                    </a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Header",
        props: ["name","poste","city","email","social","other"],
        data(){
            return {
                cv_label: "Télécharger le CV",
                cv_icon: "file-download",
                cv_pdf: "../static/resume/cv.pdf"
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
        padding-left: 10px;
    }

    .header img {
        height: 230px;
        float: left;
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

    .coordonnees span.break {
        margin-top: 10px;
    }

    .coordonnees span {
        display: block;
    }

    .coordonnees span a {
        color: #000;
    }

    .coordonnees span .fa-icon {
        color: #337ab7;
        margin-right: 5px;
    }

    .download-buttons > .btn {
        float: right;
        background-color: #337ab7;
    }

    .download-buttons > .btn > .fa-icon {
        margin: 0px 3px 0px 0px;
        bottom: 1px;
        position: relative;
    }

</style>