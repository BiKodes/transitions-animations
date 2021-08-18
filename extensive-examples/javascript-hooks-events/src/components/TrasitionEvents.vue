<template>
    <div class="text-primary py-4 text-center" style="border: 1px solid #000">

        <transition 
            name="button" 
            mode="out-in"
            @before-enter="beforeEnter"
            @after-enter="afterEnter"
            @enter="enter"
            @before-leave="beforeLeave"
            @after-leave="afterLeave"
            @leave="leave"
            >
            <button
            class="btn btn-primary"
            @click.prevent="onShowButton()"
            v-if="!showOnButton">
            Off
            </button>

             <button
            class="btn btn-primary"
            v-else
            @click.prevent="onShowButton()">
            On
            </button>
        </transition>
        
    </div>
</template>

<script> 
export default {
    name: 'AnimateButton',

    data() {
        return {
            showOnButton: true,
        }
    },

    methods: {
        onShowButton(){
            this.showOnButton = !this.showOnButton;
        },

        beforeEnter(){
          console.log('before Enter')  
        },

        afterEnter(){
          console.log('after Enter')   
        },

        enter(){
          console.log('enter')   
        },

        beforeLeave(){
            console.log('before Leave')
        },

        afterLeave(){
            console.log('after Leave')
        },

        leave(){
            console.log('leave')
        }

    },
};
</script>

<style scoped>

.button-enter-from,
.button-leave-to {
    opacity: 0;
    transform: translateX(-30px);
}

.button-enter-to,
.button-leave-from {
    opacity: 1;
    transform: translateX(0px);
}

.button-enter-active,
.button-leave-active {
    transition: all 1s;
}

</style>