<template>
    <div id="demo">
        <transition>
            <button :key="docState">
                {{ buttonMessage }}
            </button>
        </transition>
    </div>
</template>

<script>
export default {

    computed: {
        buttonMessage() {
            switch (this.docState) {
                case 'saved':
                    return 'Edit'

                case 'edited':
                    return 'Save'

                case 'editing':
                    return 'Cancel'
            }
        }
    }
    
}
</script>