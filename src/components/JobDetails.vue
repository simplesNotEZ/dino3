<template>
    <section id="job-details">
        <h2>Job Details</h2>
        <h4>{{listing.title}}</h4>
        <p>{{listing.description}}</p>
        
    </section>

</template>

<script>
export default {
    name: "JobDetails",
    components: {

    },
    methods: {

    },
    props: ['listing']
}


</script>

<style>


</style>