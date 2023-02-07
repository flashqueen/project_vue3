<template>
    <div>
        <p v-if="esta_reagindo">Estou investigando no momento</p>
        <p v-else="">Estou em busca de novas reações.</p>
        <p>A reação dos seguintes elementos:</p>
        <ul>
            <li v-for="investigation in inv_reacoes">{{ investigation }}</li>
            <li>+Anemo</li>
        </ul>
        <p>Acho desnecessário tratar de outras reações como:</p>
        <ul>
            <li v-for="investigation in not_reacoes">
                {{ investigation.element }}
            </li>
        </ul>
        <div>
            <button @click="showEmail">{{ textoBotao }}</button>
        </div>
        <p v-show="mostrar_email">Envie os relatórios de pesquisa para: {{ email }}</p>
        <p class="teste">Se realmente quiser me ajudar, venha <a v-bind:href="meu_link" target="_blank">aqui</a></p>
        <Picture />
    </div>
</template>

<script>
import Picture from './Picture.vue'

export default {
    name: "Info",
    components: {
        Picture
    },
    props: {
        email: String,
        esta_reagindo: Boolean
    },
    data() {
        return {
            mostrar_email: false,
            meu_link: "https://google.com",
            textoBotao: "Colaborar",
            inv_reacoes: ['Cryo', 'Pyro', 'Hydro'],
            not_reacoes: [
                { id: 1, element: 'geo' },
                { id: 2, element: 'electro' },
                { id: 3, element: 'physical' }
            ]
        }
    },
    methods: {
        showEmail() {
            this.mostrar_email = !this.mostrar_email;
            if (!this.mostrar_email) {
                this.textoBotao = "Enviar Análises"
            } else {
                this.textoBotao = "Esconder e-mail"
            }
        }
    }

}
</script>

<style>
.paragrafo-pai {
    color: blueviolet;
}
</style>