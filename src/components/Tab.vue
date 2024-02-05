<template>
    <div class="tab-content" v-show="title == selectedTitle">
        <slot />
    </div>
</template>

<script>
import { inject } from 'vue';
export default {
    props: ['title'],
    setup() {
        const selectedTitle = inject("seletedTitle")


        return {
            selectedTitle
        }
    }
    

}
</script>
<style scoped>
.tab-content {
    padding: 20px;
    border: 1px solid #ccc;
    min-height: 400px;
    border-radius: 5px;
    box-shadow: 0 3px 5px rgba(0, 0, 0, .05);
}

</style>