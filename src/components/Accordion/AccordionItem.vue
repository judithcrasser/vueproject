<template>
    <div v-if="musician">
        <h1></h1>
    </div>
</template>

<script>
export default {
    props: ['id'],
    data() {
        return {
            musician: null
        }
    },
    mounted() {
        fetch('http://localhost:3000' + this.id)
            .then(res => res.json())
            .then(data => this.musician = data)
            .catch(err => console.log(err.message))
    }
}
</script>