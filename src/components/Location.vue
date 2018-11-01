<template>
    <div>
        <h3 class="title with-icon"><icon class="cat-title" :name="icon"></icon> {{ title }}</h3>
        <div class="grid-block">
            <iframe src="https://www.google.com/maps/embed/v1/place?q=Auckland, New Zealand&key=AIzaSyClEWLh20lxrQBFR7omuuVESviszPxONyk"
                    width="100%" height="100%" frameborder="0" style="border:0"></iframe>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Location",
        data() {
            return {
                title: "Géolocalisation",
                icon: "location-arrow"
            }
        },
    }
</script>

<style scoped>

</style>