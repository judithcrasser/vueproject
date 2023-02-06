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
                                    viewBox="0 0 512 512">
                                    <path
                                        d="M233.4 406.6c12.5 12.5 32.8 12.5 45.3 0l192-192c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0L256 338.7 86.6 169.4c-12.5-12.5-32.8-12.5-45.3 0s-12.5 32.8 0 45.3l192 192z" />
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
