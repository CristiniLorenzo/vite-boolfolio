<script>
import axios from 'axios';

export default {
    name: 'ProjectList',
    data() {
        return {
            projects: []
        };
    },
    methods: {
        getProjects() {
            axios.get('http://127.0.0.1:8000/api/projects')
            .then((response) => {
                this.projects = response.data.results;
            });
        }
    },
    mounted() {
        this.getProjects();
    }
}
</script>

<template>
    <div class="container">
        <h1>All Projects</h1>

        <div class="row row-cols-4">
            <div v-for="project in projects" class="col">

                <div class="card my-2">
                    <!-- <img src="..." class="card-img-top" alt="..."> -->
                    <div class="card-body">
                        <h5 class="card-title">{{ project.name }}</h5>
                        <div class="card-text my-3"><strong>Client name:</strong> {{ project.client_name }}</div>
                        <p v-if="project.summary" class="card-text">{{ project.summary }}</p>
                        <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
</style>