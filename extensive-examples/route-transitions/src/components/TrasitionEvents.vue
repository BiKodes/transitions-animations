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
            @enter-cancelled="enterCancel"
            @leave-cancelled="leaveCancel"
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
            enterInterval: '',
            leaveInterval: ''
        };
    },

    methods: {
        onShowButton(){
            this.showOnButton = !this.showOnButton;
        },

        beforeEnter(el){
            console.log('before enter')
            el.style.opacity = 0; 
        },

        enterCancel(){
            clearInterval(this.enterInterval)
        },

        leaveCancel() {
            clearInterval(this.leaveInterval)
        },

        afterEnter(){
          console.log('after Enter')   
        },

        enter(el, done){
            console.log('enter');
            let step = 0.01
            let opacity = 0;

            this.enterInterval = setInterval(() => {
                console.log('enter interval running');
                opacity += step;
                el.style.opacity = opacity;

                if (opacity >= 1) {
                    clearInterval(this.enterInterval);
                    done();
                } 
            }, 10);
        },

        beforeLeave(el){
            console.log('before leave')
            el.style.opacity = 1; 
        },

        afterLeave(){
            console.log('after Leave')
        },

        leave(el, done){
            console.log('leave');
            let step = 0.01
            let opacity = 1;

            this.leaveInterval = setInterval(() => {
                console.log('leave interval running');
                opacity -= step;
                el.style.opacity = opacity;

                if (opacity <= 0) {
                    clearInterval(this.leaveInterval);
                    done();
                } 
            }, 10);
        }

    },
};
</script>

<style scoped>
/* 
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
} */
 
</style>