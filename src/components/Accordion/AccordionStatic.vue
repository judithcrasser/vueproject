<template>
    <section class="accordion-section">
        <div class="row">
            <div class="column accordion">
                <div class="accordion-item">
                    <div class="title"
                        @click="toggleAccordion()">

                        <div class="text">
                            Shostakovitch
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
                        v-show="isOpen">
                        <div class="image">
                            <img src="https://img.welt.de/img/kultur/buehne-konzert/mobile165579455/8171620727-ci23x11-w1136/Der-sowjetische-Komponist-Dimitri-Schostakowitsch.jpg"
                                alt="schostakowitsch">
                        </div>
                        <div class="text-wrapper">
                            <p class="text">
                                Shostakovich was a Soviet-era Russian composer and pianist who became internationally
                                known after the premiere of his First Symphony in
                                1926 and was regarded throughout his life as a major composer.
                            </p>
                            <p class="text">
                                Some of my favourite pieces are:
                            </p>
                            <ul>
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
            isOpen: false,
        };
    },

    methods: {
        toggleAccordion() {
            this.isOpen = !this.isOpen;
        },
    },
};
</script>

