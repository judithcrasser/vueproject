<template>
    <div id="demo">
        <ul class="level-0-wrp"
            v-if="menuitems.length">
            <li class="level-0"
                v-for="(menu, index) in menuitems"
                :key="index"
                v-if="menuitems">
                <a class="title"
                    @click="toggleAccordion(menu.item_name)">{{ menu.item_name }}</a>
                <ul class="level-1-wrp"
                    v-if="menu.childrens">
                    <li class="level-1"
                        v-for="(submenuone, indexone) in menu.childrens"
                        :key="indexone"
                        v-if="isOpen && menu.item_name === selected">
                        <a class="title">{{ submenuone.item_name }}</a>
                    </li>
                </ul>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data() {
        return {
            isOpen: false,
            selected: '',
            menuitems: []
        }
    },
    methods: {
        toggleAccordion(item) {
            item == this.selected ? this.isOpen = !this.isOpen : this.isOpen = true
            this.selected = item
        }
    },
    mounted() {
        fetch('http://localhost:3000/menuitems')
            .then(res => res.json())
            .then(data => this.menuitems = data)
            .catch(err => console.log(err.message))
    }
}
</script>