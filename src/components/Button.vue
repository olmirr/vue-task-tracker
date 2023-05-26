<template>
    <button @click='$emit("btn-click")' class="btn" :style="{background: color}" >{{ text }}</button>
</template>


<script>
    export default {
        name: 'my-button',
        props: {
            text: String,
            color: String
        },
        emits: ['btn-click']
    }
</script>
