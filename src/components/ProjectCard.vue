<script>
export default {
    name: "ProjectCard",
    props: ["project"],
    data: () => {
        return {
            redirect: "/portfolio/"
        }
    },
    mounted() {
        this.redirect += this.project.file
    }
}
</script>


<template>
    <div id="projectCard" v-on:click="$router.push(redirect)">
        <h4>{{ project.name }}</h4>
        <img v-bind:src="require('../assets/' + project.image)" v-bind:alt="project.description"/>
        <p class="description">{{ project.description }}</p>
        <ul class="categories">
            <li v-for="category in project.categories" v-bind:key="category" class="category">{{ category }}</li>
        </ul>
    </div>
</template>


<style scoped>
#projectCard {
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    color: #C8C8C8;
    transition: 0.1s;
    padding: 20px;
}

#projectCard:hover {
    background-color: #0B111A;
}

h4 {
    font-weight: bold;
    font-size: 20px;
}

img {
    margin-left: auto;
    margin-right: auto;
    max-width: 100%;
    height: 80%;
    border-radius: 10px;
}

.description {
    font-size: 15px;
    text-overflow: ellipsis;
}

.categories {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
}

.category {
    list-style: none;
    font-size: 15px;
    font-weight: bold;
}
</style>
