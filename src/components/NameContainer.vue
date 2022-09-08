<template>
    <div>
        <Welcome :name="this.name"></Welcome>
        <Name @new-name="passName($event)"></Name>
    </div>
</template>

<script>
import Welcome from './Welcome.vue';
import Name from './Name.vue';

    export default {
    name: "NameContainer",
    data() {
        return {
            name: ""
        };
    },
    methods: {
        passName: function($event){
            this.name = $event
            console.log('Parente name: ', this.name)
        }
    },
    computed: {},
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
        console.log('lifecycle hook: updated', this)
    },
    beforeUnmount() {
        console.log("lifecycle hook: beforeUnmount");
    },
    unmounted() {
        console.log("lifecycle hook: unmounted");
    },
    components: { Welcome, Name }
}
</script>

<style lang="scss" scoped>

</style>