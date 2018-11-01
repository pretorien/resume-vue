<template>
    <div>
        <h3 class="title with-icon"><icon class="cat-title" :name="icon"></icon> {{ title }}</h3>
        <ul class="timeline">
            <li v-for="degree in sortedDegrees" class="timeline-inverted">
                <div class="timeline-badge info">{{ degree.start_year }}</div>
                <div class="timeline-panel grid-block">
                    <div class="timeline-heading">
                        <h4 class="timeline-title"><span class="degree-name">{{ degree.name }} </span>- {{ degree.school }}</h4>
                        <p class="timeline-info">
                            <span v-if="degree.start_year"><icon name="calendar"></icon>{{ degree.start_year }} - {{ degree.end_year }}</span>
                            <span v-if="degree.city"><icon name="map-marker"></icon>{{ degree.city }}</span>
                            <span v-if="degree.night == true"><icon name="moon"></icon>{{ nightly }}</span>
                        </p>
                    </div>
                    <div class="timeline-body">
                        {{ degree.description }}
                    </div>
                </div>
            </li>
        </ul>
    </div>

</template>

<script>

    export default {
        name: "EducationHistory",
        props: ["degrees"],
        data() {
            return {
                title: "Formations",
                icon: "graduation-cap",
                nightly: "Cours du soir"
            }
        },
        computed: {
            sortedDegrees: function () {
                return this.degrees.sort((a, b) => b.start_year - a.start_year);
            }
        }
    }
</script>

<style scoped>
</style>