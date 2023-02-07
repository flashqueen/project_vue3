<template>
    <div>
        <h2>Sou apenas um viajante como você {{ nome }}.</h2>
        <Info :email="email" :esta_reagindo=true />
        <Form />
    </div>
</template>

<script>
import Info from './Info.vue';
import Form from './Form.vue';

export default {
    name: "Pessoa",
    components: {
        Info,
        Form
    },
    data() {
        return {
            nome: "flashqueen",
            email: "flashq@akade.com"
        }
    }
}
</script>