<script>
export default {
    name: 'ProjectCard',
    props: {
        projectInfo: Object
    }
}    
</script>

<template>
    <div class="col">
        <div class="card my-2">
            <!-- <img src="..." class="card-img-top" alt="..."> -->
            <div class="card-body">
                <h5 class="card-title">{{ projectInfo.name }}</h5>
                <div class="card-text my-3"><strong>Client name:</strong> {{ projectInfo.client_name }}</div>
                <p v-if="projectInfo.summary" class="card-text">{{ projectInfo.summary }}</p>
                <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
            </div>
        </div>
    </div>

</template>