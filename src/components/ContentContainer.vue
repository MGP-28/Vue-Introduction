<template>
    <div class="contentContainer nav">
        <button :class="isActive(1)" @click="changeIndex(1)">Name</button>
        <button :class="isActive(2)" @click="changeIndex(2)">Message</button>
        <button :class="isActive(3)" @click="changeIndex(3)">User card</button>
    </div>
    <div class="contentContainer">
        <NameContainer v-show="index === 1"></NameContainer>
        <FreeText v-show="index === 2"></FreeText>
        <UserCard v-show="index === 3"></UserCard>
    </div>
</template>

<script>
import NameContainer from './NameContainer.vue';
import FreeText from './FreeText.vue';
import UserCard from './userCard.vue';
    export default {
    name: "ContentContainer",
    data() {
        return {
            index: 1
        };
    },
    methods: {
        changeIndex: function (index) {
            this.index = index;
        },
        isActive: function (index){
            return this.index === index ? 'active' : ''
        }
    },
    computed: {
    },
    beforeCreate() {
        console.log("lifecycle hook: beforeCreated");
    },
    created() {
        console.log("lifecycle hook: created");
    },
    beforeMount() {
        console.log("lifecycle hook: beforeMount");
    },
    mounted() {
        console.log("lifecycle hook: mounted");
    },
    beforeUpdate() {
        console.log("lifecycle hook: beforeUpdate");
    },
    updated() {
        console.log("lifecycle hook: updated", this);
    },
    beforeUnmount() {
        console.log("lifecycle hook: beforeUnmount");
    },
    unmounted() {
        console.log("lifecycle hook: unmounted");
    },
    components: { NameContainer, FreeText, UserCard }
}
</script>

<style scoped>
    .nav{
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }
    button {
        border: 0.5px solid blanchedalmond;
        border-radius: 0;
    }
    .active {
        background-color: blanchedalmond;
        color: black;
        font-size: 1.1rem;
        scale: 1.05;
    }
</style>