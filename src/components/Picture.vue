<template>
    <div>
        <img :src="avatar" :alt="descricao">
        <MudarImagem @mudar-imagem="trocarImagem" />
    </div>
</template>

<script>
import MudarImagem from './MudarImagem.vue';

export default {
    name: "Picture",
    components: {
        MudarImagem
    },
    data() {
        return {
            avatar: "/img/wanderer.png",
            descricao: "Andarilho"
        };
    },
    methods: {
        trocarImagem() {
            this.avatar = "/img/wanderer_oop.png"
        }
    }
}
</script>