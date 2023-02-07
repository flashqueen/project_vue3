<template>
    <form action="" @submit="enviarFormulario($event)">
        <div>
            <h3>Tem dúvidas da minha investigação?</h3>
            <div>
                <input type="text" v-model="name">
            </div>
            <div>
                <input type="text" v-model="email">
            </div>
            <div>
                <Submit />
            </div>
            <p>conteúdo</p>
            <p>conteúdo</p>
            <p>conteúdo</p>
        </div>

    </form>

</template>

<script>

import InputText from './form/InputText.vue'
import Submit from './form/Submit.vue'

export default {
    name: "Form",
    components: {
        InputText,
        Submit
    },
    data() {
        return {
            name: "",
            email: ""
        }
    },
    methods: {
        enviarFormulario(e) {

            const name = this.name;
            const email = this.email;

            e.preventDefault();

            console.log("Formulário Enviado!")
            console.log("O nome é: " + name)
            console.log("O email é: " + email)

            // Ajax

            // Inserir no banco os dados
        }
    }
}
</script>

<style scoped>
p {
    margin: 150px;
}
</style>