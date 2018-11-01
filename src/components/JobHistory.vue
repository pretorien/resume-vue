<template>
    <div>
        <h3 class="title with-icon"><icon class="cat-title" :name="icon"></icon> {{ title }}</h3>
        <ul class="timeline">
            <li v-for="job in sortedJobs" class="timeline-inverted">
                <div class="timeline-badge info">{{ job.start_year }}</div>
                <div class="timeline-panel grid-block">
                    <div class="timeline-heading">
                        <h4 class="timeline-title"><span class="job-poste">{{ job.poste }}</span> - {{ job.title }}</h4>
                        <p class="timeline-info">
                            <icon name="calendar"></icon>{{ job.start_year }} - {{ job.end_year }}
                            <icon name="map-marker"></icon> {{ job.city }}
                        </p>
                    </div>
                    <div v-if="job.description" class="timeline-body">
                        <p>{{ job.description }}</p>
                    </div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: "WorkHistory",
        props: ["jobs"],
        data() {
            return {
                title: "Expériences professionnelles",
                icon: "briefcase"
            }
        },
        computed: {
            sortedJobs: function () {
                return this.jobs.sort((a, b) => b.start_year - a.start_year);
            }
        }
    }
</script>

<style scoped>

</style>