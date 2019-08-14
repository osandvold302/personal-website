<template>
    <div b-container class="container-projects">
        <b-row>
            <b-col class="col-text text-left" offset="1">
                <h2>Projects</h2>
            </b-col>
        </b-row>
        <template v-for="project in projects" id="project-section">
            <b-form-row class="project-rows" v-bind:key="project.title">
            <b-col class="justify-content-md-center text-center" offset-sm="1" sm="2" v-bind:key="project.title">
                <img v-bind:src="getImgUrl(project.img)" class="img-fluid" v-bind:alt="project.img" width=auto/>
            </b-col>
            <b-col id="project-summary" class="col-text text-left" sm="8" v-bind:key="project.summary">
                <h4>{{ project.title }}</h4>
                <p>{{ project.summary }}</p>
            </b-col>
            </b-form-row>
            <br v-bind:key="project.title">
        </template>
    </div>
</template>

<script>
export default {
    name: 'projects',
    components: {},
    methods: {
        getImgUrl(pic) {
            return require('../assets/'+pic)
        }
    },
    data() {
        return {
            projects: [
                {title: 'iOS Test Lab App', summary: 'The Tamino iOS Photo application was built to detect deformities and heat ' 
                + 'variations of our high temperature furnaces. I built the backend using Swift and AWS tools to connect the user ' 
                + 'to the DynamoDB table and upload images to an S3 bucket. From there, a lambda function was triggered and detected ' 
                + 'parts using a pre-built neural network.', img: 'takephotoapp.png'},
                {title: 'My Little Trader Bot', summary: 'My Little Trader Bot began from a desire to learn and understand financial '
                + 'trading algorithms based on the challenged provided by Optiver at HackDelft 2019 in Delft, Netherlands. '
                + 'My team researched various types of strategies and played the "fake" stocks, attempting to increase our profits. '
                + 'We were able to build a front-end website for monitoring our progress and allow our end user to update the various ' 
                + 'arguments to a few pre-defined algorithms.', img: 'mylittletraderbot.jpg'}
            ]
        }
    }
}

</script>

<style scoped>
.container-projects {
    padding-top: 20px;
}

#project-summary {
    padding-top: 20px;
    padding-left: 20px;
    padding-right: 20px;
}

.project-rows #project-summary {
    background-color: rgba(115,121,146,.1);
    transition: all ease 0.5s;
}

.project-rows #project-summary:hover{
    background-color:rgba(115,121,146,.4); 
}

</style>