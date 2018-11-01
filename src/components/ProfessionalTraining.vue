<template>
    <div>
        <h3 class="title with-icon"><icon class="cat-title" :name="icon"></icon> {{ title }}</h3>
        <div class="card-columns">
            <div v-for="course in sortedCourses" class="card">
                <div class="card-body">
                    <h5 class="card-title">{{ course.title }}</h5>
                    <p class="card-text">{{ course.description }}</p>
                    <p class="card-text detail">
                        <span><icon name="calendar"></icon> {{ course.year }}</span>
                        <span><icon name="school"></icon> {{ course.school }}</span>
                        <span><icon name="clock"></icon> {{ course.duration }} jours</span>
                    </p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ProfessionalTraining",
        props: ["courses"],
        data() {
            return {
                title: "Formations profesionnelles",
                icon: "book"
            }
        },
        computed: {
            sortedCourses: function () {
                return this.courses.sort((a, b) => b.year - a.year);
            }
        }
    }
</script>

<style scoped>
    .card-columns {
        margin-left:65px;
    }
    .card-title {
        color: rgb(186, 78, 78);
    }
    .card-text.detail {

     }
    .card-text.detail span {
        margin-right: 10px;
    }
</style>