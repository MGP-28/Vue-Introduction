<template>
    <div>
        <h1 v-if="freeText !== ''">{{ displayFreeText }}</h1>
        <button v-if="!isTextBoxActive" 
                @click="showTextBox">
                Clique aqui para introduzir uma mensagem
        </button>
        <input  class="inputText" 
                v-if="isTextBoxActive" 
                type="text" 
                name="" 
                placeholder="Escreva uma mensagem"
                v-model="freeText">
    </div>
</template>

<script>
    export default {
        name: "FreeText",
        data(){
            return{
                freeText: "",
                isTextBoxActive: false
            }
        },
        methods: {
            showTextBox: function(){
                this.isTextBoxActive = true
            }
        },
        computed: {
            displayFreeText(){
                return this.freeText
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
        },
        mounted(){
            console.log('lifecycle hook: mounted')
        },
        beforeUpdate(){
            console.log('lifecycle hook: beforeUpdate')
        },
        updated(){
            console.log('lifecycle hook: updated')
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