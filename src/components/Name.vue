<template>
    <div>
        <button v-if="!isTextBoxActive" 
                @click="showTextBox">
                Clique aqui para introduzir o seu nome
        </button>
        <input  class="inputText" 
                v-if="isTextBoxActive" 
                type="text" 
                name="" 
                placeholder="Introduza o seu nome"
                v-model="name"
                @input="broadcastName">
    </div>
</template>

<script>
    export default {
        name: "Name",
        data(){
            return{
                name: "",
                isTextBoxActive: false
            }
        },
        methods: {
            showTextBox: function(){
                this.isTextBoxActive = true
            },
            broadcastName: function(){
                console.log('broadcasting name: ', this.name)
                this.$emit("new-name", this.name)
            }
        },
        computed: {
            
        },
        emits:[
            "new-name"
        ],
        beforeCreate(){
            console.log('lifecycle hook: beforeCreated')
        },
        created(){
            console.log('lifecycle hook: created')
        },
        beforeMount(){
            console.log('lifecycle hook: beforeMount')
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