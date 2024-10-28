<template>
    <div class="cardCurso" v-if="curso">
        <RouterLink :to="{name: 'exibirCurso', params: {id: this.idCurso} }">
        <img class="curso-capa" :src="capa_curso" alt="Capa do curso">
        <div class="area-text" >
            <h2 class="curso-titulo">{{this.titulo}}</h2>
            <h5 class="curso-autores">{{this.criador}} • {{ this.nModulos }} Módulos</h5>
            <p class="curso-avaliacao"><i class="fa fa-star"></i> {{ this.avaliacao }}</p>
        </div>
        </RouterLink>
    </div>

    <div class="cardCurso" v-else>
        <img class="curso-capa" src="../../../assets/capa.jpg" alt="Capa do curso">
        <div class="area-text">
            <h2 class="curso-titulo"><a :href="this.link_noticia">{{ this.titulo }}</a></h2>
            <h5 class="curso-autores">{{ this.criador }} • {{ this.data_post }}</h5>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    curso: Boolean, // verificar se é curso, se false, entao é noticia
    titulo: String, //prop padrao
    criador: String, //prop padrao (representa nome do site tambem)
    data_post: String, // apenas noticia
    capa_curso: String, // prop padrao
    link_noticia: String, // apenas noticia
    avaliacao: String, // apenas p curso
    idCurso: Number, // apenas p curso
    nModulos: Number // apenas p curso
});

console.log(props);
</script>

<style lang="scss">
.cardCurso {
    width: 250px;
    height: 350px;
    margin-inline: 15px;
    box-shadow: 0px 0px 100px 3px rgba(0,0,0,0.1);
    transition: .5s all;
    overflow: hidden;
    border-radius:20px;
    margin-block: 20px;

    h2, h5, a, p {
        margin: 0;
        color: #000;
    }
    img {
        width: 100%;
    }

    a {
        text-decoration: none;
    }

    .curso-titulo {
        max-width: 20ch;
        overflow: hidden;
        text-overflow: ellipsis;

        display: -webkit-box;
        -webkit-line-clamp: 2; // Quantidade de linhas  
        -webkit-box-orient: vertical;

        font-weight: 700;
        transition: .5s;
        margin-bottom: 5px;
    }

    a:hover h2 {
        color: #990EF1;
    }
    .area-text {
        padding: 10px;
    }

    h5 {
        font-style: italic
    }
}

.cardCurso:hover {
    box-shadow: 0px 0px 50px 3px rgba(0,0,0,0.3);
    transform: scale(1.05)
}
</style>
