<template>
    <div>
        <h3 class="title with-icon"><icon :name="icon" class="cat-title"></icon> {{ title }}</h3>
        <div class="grid-block">
            <ul class="list-unstyled list-strip">
                <li v-for="language in languages">
                    <icon name="check"></icon> <span class="badge badge-green badge-right-float">{{ language.level }}</span> {{ language.name }}
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Languages",
        data() {
            return {
                title: "Langues",
                icon: "globe-americas"
            }
        },
        props: [
            'languages'
        ]
    }
</script>

<style scoped>

</style>