<template>
    <div id="demo">
        <transition 
         @before-enter="beforeEnter"
         @enter="enter"
         @after-enter="afterEnter"
         @enter-cancelled="enterCancelled"
         @before-leave="beforeLeave"
         @leave="leave"
         @after-leave="afterLeave"
         @leave-cancelled="leaveCancelled"
         :css="false">
        
        </transition>
    </div>
</template>

<script>
export default {

    methods: {

        // ENTERING
        
        beforeEnter(el) {

        },

        // the done callback is optional when
        // used in combination with CSS

        enter(el, done){
            done()
        },

        afterEnter(el){

        },

        enterCancelled(el){

        },

        // LEAVING

        beforeLeave(el){

        },

        // the done callback is optional when
        // used in combination with CSS

        leave(el, done) {
            done()
        },

        afterLeave(el){

        },

        leaveCancelled(el){
            
        }
        
    },
    
}
</script>