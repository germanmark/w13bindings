<template>
    <div>
        <h1>I'm the parent</h1>
        <a :href="myLink">Link</a>
        <span v-if="!isLeftShown && !isRightShown">0</span>
        <span v-else-if="isLeftShown && !isRightShown">1</span>
        <span v-else-if="!isLeftShown && isRightShown">1</span>
        <span v-else>2</span>

        <div id="gridContainer">
            <button @click="toggleLeft">Toggle left</button>
            <button @click="toggleRight">Toggle right</button>
            <ChildComp v-if="isLeftShown"/>
            <div v-else></div>

            <ChildComp v-if="isRightShown"/>
            <div v-else></div>

        </div>

    </div>
</template>

<script>
import ChildComp from '@/components/ChildComp.vue'
    export default {
        name : 'ParentComp',
        components: {
            ChildComp,
        },
        data() {
            return {
                myLink: "https://yahoo.ca",
                isLeftShown : true,
                isRightShown : true
            }
        },
        methods: {
            toggleLeft() {
                this.isLeftShown = !this.isLeftShown;
            },
            toggleRight() {
                this.isRightShown = !this.isRightShown;
            }
        },
    }
</script>

<style scoped>
#gridContainer {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
*{
    background-color: rgb(89, 89, 243);
    color: white;
}
span {
    margin-left: 33%;
    font-size: 3em;
}

</style>