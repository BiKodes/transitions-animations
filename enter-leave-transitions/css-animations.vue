<template>
    <div id="demo">
        <button @click="show = !show">Finya Uone</button>

        <transition name="bounce">
            <p v-if="show">
                Hatimaye siku ya hukumu ilifika baada ya kesi kusikilizwa mahakamani kwa 
                takribani mwaka mzima.

                Desemba 26 Jaji Kiongozi Nassor Mzavas alianza kutoa maelezo ya hukumu ya 
                kesi ya uhaini kwa kuchambua ushahidi wa pande zote za mashtaka na utetezi 
                hadi alipotoa hukumu Jumamosi ya Desemba 28, 1985.
     
                Baada ya kutumia saa tano Desemba 26 kuchambua ushahidi wa pande hizo, 
                Desemba 27, aliendelea kusoma hukumu hiyo wakati Mahakama ilipoendelea na kikao chake.
            </p>
        
        </transition>
        
    </div>
</template>

<script>
import Vue from 'vue';

export default {
    setup() {
        
        const Demo = {
            data() {
                return {
                    show: true
                }
            },
        }

        Vue.createApp(Demo).mount('#demo')
    }

    
}
</script>

<style scoped>

.bounce-enter-active {
    animation: bounce-in 0.5s;

}

.bounce-leave-active {
    animation: bounce-in 0.5s reverse;
}

@keyframes bounce-in {
    0% {
        transform: scale(0);
    }

    50% {
        transform: scale(1.25);
    }
    100% {
        transform: scale(1);
    }
}

</style>