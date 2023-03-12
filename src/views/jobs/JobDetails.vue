<template>
    <div>
        <h1>{{ job.title }}</h1>
        <p>The job id is {{ id }}</p>
    </div>
</template>

<script>
export default {
    props: ['id'],
    data() {
        return{
            job:null
        }
    },
    mounted() {
        fetch('http://localhost:3000/job/' + this.id)
            .then(res => res.json())
            .then(data => this.job = data)
            .catch(err => console.log(err.message))
    }
    // data() {
    //     return {
    //         id: this.$route.params.id
    //     }
    // }
}
</script>

<style>

</style>