<template>
    <div class="text-center">
        <transition>
            <p v-if="showParagraph">Kwani Jana Kuliendaje?.</p>

        </transition>
        
        <button
            class="btn btn-primary"
            @click.prevent="onToggle()"
        >
            Finya
        </button>
    </div>
</template>

<script>
export default {
    name: 'TheParagraph',

    data(){
        return {
            showParagraph: true
        };
    },

    methods: {
        onToggle(){
            this.showParagraph = !this.showParagraph;
        }
    },

    
}
</script>

<style scoped>
.v-enter-from {
    opacity: 0;
    transform: translateY(-10px);
}

.v-enter-to {
    opacity: 1;
    transform: translateY(0px);  
}

.v-enter-active {
    transition: all 1s;
    
}

.v-leave-from {
    opacity: 1;
    transform: translateY(0px);
}

.v-leave-to {
    opacity: 0;
    transform: translateY(-10px);
}

.v-leave-active {
    transition: all 1s;
}
</style>