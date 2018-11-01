<template>
    <div>
        <h3 class="title with-icon"><icon class="cat-title" :name="icon"></icon> {{ title }}</h3>
        <div v-for="skill in skills" style="margin-bottom: 25px">
            <div class="grid-block">
                <h5>{{ skill.category }}</h5>
                <div v-for="(item, index) in skill.data" class="progress">
                    <div :class="'progress-bar ' + bg_class[(index%bg_class.length)] + ' w-' + item.level" role="progressbar">
                        <span class="progress-type">{{ item.name }}</span>
                    </div>
                </div>
                <div class="grille-evaluation">
                    <div class="evaluation evaluation-beginner"><span>Débutant</span></div>
                    <div class="evaluation evaluation-basic"><span>Basique</span></div>
                    <div class="evaluation evaluation-advance"><span>Avancé</span></div>
                    <div class="evaluation evaluation-competent"><span>Compétent</span></div>
                    <div class="evaluation evaluation-expert"><span>Expert</span></div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "SkillsList",
        props: ["skills"],
        data(){
            return {
                icon: "code",
                title: "Compétences",
                bg_class: [
                    'bg-grey',
                    'bg-red'
                ]
            }
        }
    }
</script>

<style scoped>

    .progress {
        margin: 10px 0;
        height: 25px;
    }
    .progress-bar {
        text-align: left;
        white-space: nowrap;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        cursor: pointer;
    }

    .bg-red {
        background-color: rgb(186, 78, 78);
    }

    .bg-grey {
        background-color: rgb(75, 111, 120);
    }

    .progress-bar > .progress-type {
        padding-left: 5px;
        font-weight: bold;
        color: #FFF;
    }

    .grille-evaluation {
        min-height: 15px;
        border-bottom: 2px solid rgb(160, 160, 160);
        margin-bottom: 25px;
    }

    .grille-evaluation .evaluation {
        position: relative;
        float: left;
        min-height: 15px;
        border-width: 0px;
        border-style: solid;
        border-color: rgb(160, 160, 160);
        border-left-width: 2px;
        height: 15px;
    }

    .grille-evaluation .evaluation span {
        position: relative;
        display: inline-block;
        bottom: -15px;
        width: 100%;
        font-weight: 700;
        font-size: 0.85em;
        color: rgb(160, 160, 160);
        text-align: right;
    }

    .grille-evaluation .evaluation-beginner {
        border-left-width: 0px;
        width: 20%;
    }

    .grille-evaluation .evaluation-basic {
        width: 20%;
    }

    .grille-evaluation .evaluation-advance {
        width: 20%;
    }

    .grille-evaluation .evaluation-competent {
        width: 20%;
    }

    .grille-evaluation .evaluation-expert {
        width: 20%;
        border-right-width: 2px;
    }

    .w-beginner {
        width:20%;
    }

    .w-basic {
        width:40%;
    }

    .w-advance {
        width:60%;
    }

    .w-competent {
        width:80%;
    }

    .w-expert {
        width:100%;
    }

</style>