<script lang="ts">
import aFera from '@/assets/imagens-filme/filme-a-fera.jpg';
import alvoSecreto from '@/assets/imagens-filme/filme-alvo-secreto.jpg';
import capitaoAmerica from '@/assets/imagens-filme/filme-capitao-america.jpg';
import comoEuEraAntesDVoce from '@/assets/imagens-filme/filme-como-eu-era-antes-de-voce.jpg';
import pecadores from '@/assets/imagens-filme/filme-pecadores.jpg';
import FilmeItem from './components/FilmeItem.vue';


export default {
    data() {
        return {
            favoritos: 0,
            assistisdos: 0,
            pesquisa: '', 

            listaDeFilmes: [
                {
                    id: "f1",
                    nome: "A Fera",
                    descricao: "O Dr. Nate Samuels, depois de perder a esposa, viaja com suas filhas para uma reserva na África do Sul — um lugar que tinha significado pra ele. Mas a viagem vira pesadelo quando eles são perseguidos por um leão selvagem.",
                    ano: "2022",
                    imagem: aFera
                },
                {
                    id: "f2",
                    nome: "Alvo Secreto",
                    descricao: "Um assassino de aluguel da CIA descobre que sua divisão foi encerrada há muito tempo. Ele parte para descobrir quem realmente vinha lhe dando ordens.",
                    ano: "2024",
                    imagem: alvoSecreto
                },
                {
                    id: "f3",
                    nome: "Capitão America",
                    descricao: "Sam Wilson assume oficialmente o papel de Capitão América após Steve Rogers. Ele se vê envolvido em uma conspiração internacional quando o presidente Thaddeus Ross manda investigar itens confidenciais roubados; ele precisa impedir que a trama cause um caos global.",
                    ano: "2025",
                    imagem: capitaoAmerica
                },
                {
                    id: "f4",
                    nome: "Como eu era antes de você",
                    descricao: "Louisa “Lou” Clark, uma jovem de origem modesta, aceita cuidar de Will Traynor, um homem rico que ficou tetraplégico após um acidente. Ela tenta mostrar a ele que ainda há motivos para viver, e entre os dois nasce uma ligação profunda.",
                    ano: "2016",
                    imagem: comoEuEraAntesDVoce
                },
                {
                    id: "f5",
                    nome: "Pecadores",
                    descricao: "Dois irmãos gêmeos retornam à cidade natal para reconstruir suas vidas, mas passado e traumas revivem quando uma força sobrenatural ameaça sua comunidade. É um thriller com elementos sobrenaturais, ambientado no Delta do Mississippi.",
                    ano: "2025",
                    imagem: pecadores
                }],
            mensagemFavoritos: '',
            mensagemAssistidos: ''
        }
    },
    methods: {
        contadorFavoritos(filme: any) {
            this.favoritos++
            this.mensagemFavoritos = `${filme.nome} adicionado aos favoritos`

            setTimeout(() => {
                this.mensagemFavoritos = ''
            }, 3000)

        },
        contadorAssistidos(filme: any) {
            this.assistisdos++
            this.mensagemAssistidos = `${filme.nome} adicionado ao Assistidos`

            setTimeout(() => {
                this.mensagemAssistidos = ''
            }, 3000)
        }
    },


    components: { FilmeItem }

}
</script>

<template>
    
    <FilmeItem v-for="item in listaDeFilmes" :key="item.id" :filme="item" @adicionar-aos-favoritos="contadorFavoritos"
        @marcar-filme-assistido="contadorAssistidos" />

        <div v-if="mensagemFavoritos">
            <h3>{{ mensagemFavoritos }}</h3>
        </div>
        <div v-if="mensagemAssistidos">
            <h3>{{ mensagemAssistidos }}</h3>
        </div>


</template>