<template>
    <!-- <div>
        {{firstName}}{{lastName}}
        {{objectData}}
    </div> -->
    <h1>This is the component</h1>
    <slot>
    </slot>    
</template>
<script>
export default {
    // props:['firstName','lastName','objectData'],
    // props:['lastName'],
    // props:['']
    props:{
        firstName:String,
        objectData:Object
    }
}
</script>
<style>
    
</style>