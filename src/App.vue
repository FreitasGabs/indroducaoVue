<script setup>
// aqui teremos a lógica (função, import, variável, etc)

import coracao from "../src/assets/heart_empty.svg"
import curtida from "../src/assets/heart_curtido.svg"
import { ref } from "vue";

//fazendo a lógica por trás de um "like"
const imagens = ref([
  { src: coracao, isLiked: false },
  { src: coracao, isLiked: false },
  { src: coracao, isLiked: false }
]);

function like(index) {
  imagens.value[index].isLiked = !imagens.value[index].isLiked;
  imagens.value[index].src = imagens.value[index].isLiked ? curtida : coracao;
}
</script>


<template>
<!-- aqui ficam as tags, ou seja, tudo que vai ser renderizado  -->

 <header>
  <h1>Vue</h1>
  <input type="text">
 </header>

 <main>
  <section>
    <div>
      <p>17 de ago, 2024</p>

      <!-- para renderizar um dado da lógica, se for em uma tag - <tag>{{  }}</tag>; -->
      <!-- para renderizar em atributos, vamos usar o v-bind - : (atalho pro v-bind é dois pontos) -->
      <img :src="imagens[0].src" alt="Coração para dar 'curtida' na publicação" @click="like(0)">
    </div>

    <h3>O que é linguagem de programação? Conheça as principais</h3>
    <p>Uma das mais populares vertentes da tecnologia da informação, a área de programação segue tendo muita demanda de trabalho justamente pela velocidade com que dispositivos tecnológicos vêm avançando.</p>
  </section>

  <section>
    <div>
      <p>12 de jul, 2024</p>
      <img :src="imagens[1].src" alt="Coração para dar 'curtida' na publicação" @click="like(1)">
    </div>

    <h3>GitHub agora permite fazer login sem precisar de senha</h3>
    <p>O GitHub anunciou nesta quarta-feira (12) o acesso a partir das passkeys, método de autenticação sem senhas. A novidade está disponível em uma versão beta pública e pode substituir a autenticação em dois fatores.</p>
  </section>

  <section>
    <div>
      <p>21 de jun, 2024</p>
      <img :src="imagens[2].src" alt="Coração para dar 'curtida' na publicação" @click="like(2)">
    </div>

    <h3>Por que os hiperlinks são azuis em sua maioria?</h3>
    <p>Quem navega na internet, certamente já percebeu que ela conta com diversos recursos para tornar a nossa vida mais fácil. Entre essas opções podemos mencionar os hiperlinks - uma palavra ou termo clicável que direciona o leitor.</p>
  </section>
 </main>
</template>


<!-- avisar que não é css, é scss -->
<style scoped lang="scss">
/* todo o estilo */

$cor-bg-destaque: #17171A;
$cor-bg: black;
$cor-texto-destaque: #E07B67;
$cor-texto: white;
$font-titulos: "Space Grotesk";
$font-texto: "Inter"; 

body {
  background-color: $cor-bg;
}

header{
  background-color: $cor-bg-destaque;
  color: $cor-texto-destaque;
  font-family: $font-titulos;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  padding: 1.5em;
  height: 15vh;
}

main {
  background-color: $cor-bg;
  font-family: $font-texto;
  color: $cor-texto;

  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  height: 85vh;
}

section {
  background-color: $cor-bg-destaque;
  margin: 2em;
  padding: 1.5em;
  width: 50vw;

    h3{
      font-family: $font-titulos;
    }

    div {
      color: $cor-texto-destaque;

      display: flex;
      justify-content: space-between;
    }
}
</style>




