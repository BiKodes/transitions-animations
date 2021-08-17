<template>
    <div id="demo">
       <transition>
           <button v-if="docState === 'saved'" key="saved">
               Edit
           </button>

           <button v-else-if="docSate === 'edited'" key="edited">
               Save
           </button>

           <button v-else-if="docState === 'editing'" key="editing">
               Cancel
           </button>
       </transition> 
    </div>
</template>

<script>
export default {
    
}
</script>