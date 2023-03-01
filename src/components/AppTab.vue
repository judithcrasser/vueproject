<template>
    <div>
        <app-tabs :tabList="tabList">
            <template v-slot:tabPanel-1> Frontends Content </template>
            <template v-slot:tabPanel-2> Kunst Content </template>
            <template v-slot:tabPanel-3> Musik Content </template>
        </app-tabs>
    </div>
</template>

<script>
import AppTabs from "./AppTabs.vue"

export default {
    components: {
        AppTabs
    },
    data() {
        return {
            tabList: ["Frontends", "Kunst", "Musik"]
        }
    }
}
</script>
