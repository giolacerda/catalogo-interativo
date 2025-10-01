<script lang="ts">
export default {
    props: {
        filme: { type: Object, required: true }
    },

    methods: {
        adicionarFavoritos(){this.$emit('adicionar-aos-favoritos', this.filme)},
        marcarAssistido() {this.$emit('marcar-filme-assistido', this.filme)}
    }
}
</script>

<template>
    <section class="corpo_card">
        <img :src="filme.imagem">
        {{ filme.nome }} - {{ filme.ano }}

        <button class="botao_favoritos" @click="adicionarFavoritos">
            <img src="@/assets/icons/favorito.png" alt="icone de favoritos">
        </button>

        <button class="botao-assistidos" @click="marcarAssistido">
            <img src="@/assets/icons/marca-de-verificacao" alt="icone de verificado">
        </button>
   
   </section>
</template>
