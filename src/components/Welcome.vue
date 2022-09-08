<template>
    <div
        v-if="name !== ''" 
        @new-name="updateName">
        <h2>{{ displayWelcomeMessage }}</h2>
    </div>
</template>

<script>
    export default {
        name: "Welcome",
        props: [
            'name'
        ],
        data(){
            return{
                timeOfDayMessage: ""
            }
        },
        methods: {
            getTimeOfDayMessage: function(){
                const hour = new Date().getHours();
                if(hour >= 21) return 'Boa noite'
                if(hour >= 12) return 'Boa tarde'
                if(hour >= 7) return 'Bom dia'
                return 'Boa noite'
            }
        },
        computed: {
            displayWelcomeMessage(){
                return `${this.timeOfDayMessage}, ${this.name}`
            }
        },
        beforeCreate(){
            console.log('lifecycle hook: beforeCreated')
        },
        created(){
            console.log('lifecycle hook: created')
        },
        beforeMount(){
            console.log('lifecycle hook: beforeMount')
            this.timeOfDayMessage = this.getTimeOfDayMessage()
        },
        mounted(){
            console.log('lifecycle hook: mounted')
        },
        beforeUpdate(){
            console.log('lifecycle hook: beforeUpdate')
        },
        updated(){
            console.log('lifecycle hook: updated', this)
        },
        beforeUnmount(){
            console.log('lifecycle hook: beforeUnmount')
        },
        unmounted(){
            console.log('lifecycle hook: unmounted')
        }
    }
</script>

<style scoped>

</style>