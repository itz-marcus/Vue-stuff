<template lang="">
    <div class="card">
        <h1>
            <slot name="slotTitle">
                404 Titles
            </slot>
        </h1>
        <h1>
            <slot>
                404 default
            </slot>
        </h1>
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
    div{
        border: 3px black solid;
        border-radius: 20px;
        width: 300px;
        margin: 10px;
        justify-content: center;
    }

</style>