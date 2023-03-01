<template>
    <section class="accordion-section">
        <div class="row">
            <div v-if="musicians.length"
                class="column accordion">
                <div v-for="musician in musicians"
                    :key="musician.id"
                    class="accordion-item">

                    <div class="title"
                        @click="toggleAccordion()">

                        <div class="text">
                            {{ musician.name }}
                        </div>

                        <div class="chevron-wrap">
                            <div class="chevron"
                                :class="{
                                    'up': isOpen
                                }">
                                <svg xmlns="http://www.w3.org/2000/svg"
                                    xmlns:xlink="http://www.w3.org/1999/xlink"
                                    width="800px"
                                    height="800px"
                                    viewBox="0 0 512 512"
                                    version="1.1">
                                    <title>chevron-down</title>
                                    <g id="Page-1"
                                        stroke="none"
                                        stroke-width="1"
                                        fill="none"
                                        fill-rule="evenodd">
                                        <g id="add"
                                            fill="#000000"
                                            transform="translate(80.915055, 157.440000)">
                                            <polygon id="Path-19"
                                                points="320 0 350.169889 30.1698893 175.084945 205.254834 0 30.1698893 30.1698893 0 175.084945 144.898278">

                                            </polygon>
                                        </g>
                                    </g>
                                </svg>
                            </div>
                        </div>
                    </div>

                    <div class="content"
                        v-if="isOpen">
                        <div class="image">
                            <img :src="musician.image"
                                :alt="musician.name">
                        </div>
                        <div class="text-wrapper">
                            <p class="text">
                                {{ musician.description }}
                            </p>
                            <p class="text">
                                Some of my favourite pieces are:
                            </p>
                            <ul class="list">
                                <li>
                                    Symphony No. 9
                                </li>
                                <li>
                                    Cello Concerto No. 1 in E-flat major, Opus 107
                                </li>
                                <li>
                                    Symphony No. 7
                                </li>
                            </ul>
                        </div>

                    </div>

                </div>
            </div>
        </div>
    </section>
</template>

<script>


export default {
    data() {
        return {
            musicians: [],
            isOpen: false,
        };
    },

    methods: {
        toggleAccordion() {
            this.isOpen = !this.isOpen;
        },
    },

    mounted() {
        fetch('http://localhost:3000/musicians')
            .then(res => res.json())
            .then(data => this.musicians = data)
            .catch(err => console.log(err.message))
    }
};
</script>

<style lang="scss">
.accordion-section {
    min-height: 100vh;
    width: 80%;
    margin: auto;

    .accordion {
        .accordion-item {
            background-color: var(--yellow);
            margin-bottom: 1em;

            .title {
                display: flex;
                justify-content: space-between;
                padding: 1em;
                font-weight: 600;
                border-top: solid;
                border-bottom: solid;
                font-size: 2em;
                background-color: var(--yellow);

                .text {
                    background: linear-gradient(180deg, rgba(0, 0, 0, 0) 0%, rgba(0, 0, 0, 0) 26%, rgb(0, 0, 0) 25%, rgb(0, 0, 0) 90%, rgba(0, 0, 0, 0) 92%, rgba(0, 0, 0, 0) 100%);
                    color: #fff;
                    display: inline;
                    line-height: 100%;
                    letter-spacing: -1px;
                }

                &:hover {
                    cursor: pointer;
                }

                .chevron-wrap {
                    display: flex;

                    .chevron {
                        height: 1em;
                        width: fit-content;

                        &.up {
                            transform: rotate(180deg);
                        }

                        svg {
                            height: 100%;
                            width: auto;
                        }
                    }
                }
            }

            .content {
                display: flex;
                padding: 1em;
                font-weight: 600;

                .image {
                    width: 20vw;
                    margin-right: 2em;

                    @media (max-width: 1024px) {
                        width: 50%;
                    }

                    img {
                        width: inherit;
                        aspect-ratio: 1/1;
                        object-fit: cover;
                        filter: grayscale(100%);
                    }
                }

                .list {
                    flex-direction: column;

                    li {
                        list-style: disc;
                        margin-bottom: .5em;
                    }
                }
            }
        }
    }
}
</style>