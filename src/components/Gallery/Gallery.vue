<template>
    <div>
        <h1>Gallery</h1>
        <!-- <div v-for="tag in tags" :key="tag">
            <router-link :to="{ name: 'Tag', params: { tag }}">
                {{ tag }}
            </router-link>
        </div> -->
        <div v-if="error">
            {{ error }}
        </div>
        <div class="img-container">
            <div 
                v-for="musician in musicians"
                :key="musician.id"
                class="img-box">
                <img 
                :src="musician.image"
                :alt="musician.name"
                >
            </div>
            
        </div>
        <!-- <div v-else>
            Loading...
        </div> -->
    </div>
</template>

<script>
export default {
    data() {
        return {
            musicians: [],
        };
    },
    mounted() {
        fetch('http://localhost:3000/musicians')
            .then(res => res.json())
            .then(data => this.musicians = data)
            .catch(err => console.log(err.message))
    }
}
</script>

<style lang="scss">

h1 {
    padding: 2.5rem 0 0 2.5rem;
}

.img-container {
    padding: 2rem;
    display: flex;
    flex-wrap: wrap;

    .img-box {
    margin: 0.5rem;
    display: flex;
    background: blue;

    img {
    width: 200px;
    height: 200px;
    object-fit: cover;
    

    filter: grayscale(100%);


    &:hover {
        cursor: pointer;
        mix-blend-mode: screen;
        filter: grayscale(100%) contrast(150%);
        opacity: 1;
    }
   }
  }
}

</style>