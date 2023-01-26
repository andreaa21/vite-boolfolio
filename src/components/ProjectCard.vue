<script>
export default {
    name: 'ProjectCard',
    props:{
        project: Object
    }
}
</script>

<template>
    <div class="card">
        <h5>{{ project.name }}</h5>
        <div class="card-text">
            <p>{{ project.summary }}</p>
        </div>
    </div>
</template>

<style lang="scss" scoped>
    .card{
        padding: 1rem;
        border: 1px solid black;
        width: 200px;
        height: 400px;
        overflow: hidden;
    }
</style>

