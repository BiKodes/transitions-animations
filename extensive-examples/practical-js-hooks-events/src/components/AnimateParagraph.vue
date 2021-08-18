<template>
    <div>
        <transition>
            <p v-if="showParagraph">
                Kunazo aina kadhaa za tamthilia katika fasihi andishi:
                Tamthilia Cheshi/Komedia - ni mchezo wa kuchekesha. Maudhui yake huundwa kwa lengo 
                la kutumbuiza hadhira.
                Tamthilia Simanzi/Trejedia - ni mchezo uliojaa huzuni, mikasa, mikosi, visa vya 
                kutisha na aghalabu baadhi ya wahusika wakuu hufa.
                Tamthilia Simanzi-Cheshi/Trejikomedia - ni mchezo wenye visa vya kuhuzunisha lakini 
                pia unawasilisha kwa njia ya kuchekesha. Aghalabu wahusika hutumia kejeli kuchekesha 
                hadhira ijapokuwa kuna shida fulani inayowakabili. Baadhi ya wahusika wakuu hukumbwa 
                na mikasa.

                Mfano: Kifo Kisimani (na Kithaka Wa Mberia)
                Tamthilia Tatizo - ni mchezo wa kuigiza ambapo wahusika huwa na tatizo/shida kuu wanalotaka kulitatua. Tamthilia hii aghalabu hutumia mbinu ya taharuki ili kuwafanya hadhira wawe makini ili kuona jinsi tatizo hilo litakavyoishia.
                Tamthilia ya Domestiki Drama - ni mchezo unaoangazia maisha ya kawaida ya watu kama vile familia, urafiki, ndoa n.k
                Tamthilia ya Melodrama - ni mchezo ambao husisitiza sifa za wahusika kwa kuunda wahusika kuunda wahusika wenye sifa zilizopigiwa chuku na zisizobadilika. Tamthilia hizi huundwa kwa namna inayowafanya hadhira wawapende wahusika fulani na wawachukie wahusika wengine. Kwa mfano:
                Shujaa ambaye hushinda kila mara Wahusika wabaya ambao hubakia wabaya kutoka mwanzo hadi mwishi
                Wahusika wazuri ambao hufanya vitendo vizuri kutoka mwanzo hadi mwisho
                Wapenzi ambao hata wakitenganishwa bado watapendana
                Aghalabu huishia kwa raha mustarehe

            </p>
        </transition>
        

        <button
            class="btn btn-primary"
            @click.prevent="onToggle()">
            Bonyeza
        </button>
    </div>
</template>

<script>
export default {
    data() {
        return {
            showParagraph: false
        }
    },

    methods: {
        onToggle() {
            this.showParagraph = !this.showParagraph;
        }
    },
}
</script>

<style scoped>

.v-enter-active {
   animation: animate-para 1s; 
}

.v-leave-active {
   animation: animate-para 1s reverse; 
}


@keyframes animate-para {
    0% {
        opacity: 0;
        transform: translateX(0px);
    }
      25% {
        opacity: 0.25;
        transform: translateX(30px);
    }
      50% {
        opacity: 0.5;
        transform: translateX(-30px);
    }
      75% {
        opacity: 0.75;
        transform: translateX(30px);
    }
      100% {
        opacity: 1;
        transform: translateX(0px);
    }
}

</style>