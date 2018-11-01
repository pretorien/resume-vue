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
                <div class="progress-meter">
                    <div v-for="meter in skills_meter" :class="'meter meter-' + meter.direction" :style="'width: ' + meter.level +'%'"><span class="meter-text">{{ meter.label }}</span></div>
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
                ],
                skills_meter: [
                    {label:'Débutant', level:20, direction: 'left'}, // 0
                    {label:'Basique', level:15, direction: 'left'}, // 20
                    {label:'Avancé', level:25, direction: 'left'}, // 40
                    {label:'Compétent', level:25, direction: 'left'}, //60
                    {label:'Expert', level:15, direction: 'left'} // 85
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

    .w-beginner {
        width:10%;
    }

    .w-basic {
        width:20%;
    }

    .w-advance {
        width:35%;
    }

    .w-competent {
        width:60%;
    }

    .w-expert {
        width:85%;
    }

    .progress-bar > .progress-type {
        padding-left: 5px;
        font-weight: bold;
        color: #FFF;
    }

    .progress-meter {
        min-height: 15px;
        border-bottom: 2px solid rgb(160, 160, 160);
        margin-bottom: 25px;
    }

    .progress-meter > .meter {
        position: relative;
        float: left;
        min-height: 15px;
        border-width: 0px;
        border-style: solid;
        border-color: rgb(160, 160, 160);
    }

    .progress-meter > .meter-left {
        border-left-width: 2px;
    }

    .progress-meter > .meter-right {
        float: right;
        border-right-width: 2px;
    }

    .progress-meter > .meter-right:last-child {
        border-left-width: 2px;
    }

    .progress-meter > .meter > .meter-text {
        position: absolute;
        display: inline-block;
        bottom: -20px;
        width: 100%;
        font-weight: 700;
        font-size: 0.85em;
        color: rgb(160, 160, 160);
        text-align: left;
    }

    .progress-meter > .meter.meter-right > .meter-text {
        text-align: right;
    }
</style>