<template>
    <div class="tabs">
        <ul class="tabs__header">
            <li 
                v-for="title in tabTitles" 
                :key="title"
                :class="{ active: title === selectedTitle }"
                @click="selectedTitle = title"
            >
                {{ title }}
            </li>
        </ul>
        <slot />
    </div>
</template>

<script>
import { ref, provide } from 'vue';

export default {
    setup(props, { slots}) {
        const tabTitles = ref( slots.default().map((tab) => tab.props.title))
        const selectedTitle = ref(tabTitles.value[0])

        provide("seletedTitle", selectedTitle)
        return {
            selectedTitle,
            tabTitles,
        }
    }
}
</script>
<style scoped>
.tabs {
    /* border: 1px solid #ccc; */
    /* border-radius: 5px; */
    overflow: hidden;
    margin-top: 20px;
}
.tabs__header {
    display: flex;
    padding: 0;
    margin-bottom: 10px;
    list-style: none;
}
.tabs__header li {
    width: 80px;
    text-align: center;
    padding: 10px 20px;
    cursor: pointer;
    /* border-radius: 5px; */
    background-color: #f1f1f1;
    border-bottom: 1px solid #ccc;
    transition: 0.4s all ease-out;
}
.tabs__header li:hover {
    background-color: #e1e1e1;
}
.tabs__header li.active {
    background-color: #0984e3;
    /* font-weight: bold; */
    color: #fff;
}
.tab-content {
    padding: 20px;
    border-top: 1px solid #ccc;
}

</style>