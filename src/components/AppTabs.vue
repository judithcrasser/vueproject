<template>
    <div class="tabs">

        <ul>
            <li v-for="(tab, index) in tabList"
                :key="index">
                <label :for="`${_uid}${index}`"
                    v-text="tab"
                    :class="{ 'active': index + 1 === activeTab }"></label>
                <input :id="`${_uid}${index}`"
                    type="radio"
                    :name="`${_uid}-tab`"
                    :value="index + 1"
                    v-model="activeTab" />
            </li>
        </ul>

        <template v-for="(tab, index) in tabList">
            <div :key="index"
                v-if="index + 1 === activeTab"
                class="content">
                <slot :name="`tabPanel-${index + 1}`" />
            </div>
        </template>

    </div>
</template>

<script>
export default {
    props: {
        tabList: {
            type: Array,
            required: true,
        }
    },
    data() {
        return {
            activeTab: 1,
        }
    }

}
</script>

<style>
ul {
    display: flex;
}


li {
    list-style: none;
    margin-right: 20px;
}

label {
    border: 3px solid black;
    width: 75px;
    padding: 1rem 2rem;
    display: flex;
    justify-content: center;
    text-transform: uppercase;
    font-weight: bold;
    letter-spacing: 1px;
}

input {
    display: none;
}

.active {
    background-color: rgb(255, 222, 222);
    border: 3px solid blue;
    color: blue;
}

.tabs .content {
    margin: 2.5rem;
    background-color: rgb(255, 222, 222);
    width: 80%;
    padding: 2rem;
}
</style>