<template>
    <div class="modulo-conteudo">
        <h2 id="titulo_conteudo">{{ titulo }}</h2>

        <div class="area-texto">
            <div class="paragrafo" v-html="primeirotexto"></div>
            <div id="div-video" v-if="video">
                <iframe width="100%" height="100%" :src="'https://www.youtube.com/embed/' + video" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
            </div>
            <div class="paragrafo" v-html="segundotexto"></div>
        </div>
        
    </div>
</template>

<script setup>
defineProps({
    titulo: String,
    primeirotexto: String,
    video: String,
    segundotexto: String
});
</script>

<script>
</script>

<style lang="scss">
.modulo-conteudo {
    padding: 30px 40px;

    #titulo_conteudo {
        font-weight: bold;
    }

    .area-texto {
        padding-inline: 30px;

        .paragrafo {
            font-size: 20px;
            margin: 0;
            text-align: justify;
        }

        #div-video {
            display: flex;
            justify-content: center;
            padding-block: 30px;

            width:  560px;
            height: 330px;
            margin-inline: auto;
        }

        .space {
            margin-inline: 30px;
        }
    }
}

@media (max-width: 576px) {
    .modulo-conteudo {
        padding-inline: 20px;

        #titulo_conteudo {
            font-size: 22px;
        }

        .area-texto {
            padding-inline: 0;

            #div-video {
                margin: 0;
                width: 100%;
                height: 40%
            }
        }
    }
}
</style>

