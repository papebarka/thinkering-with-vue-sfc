<template>
    <button
        v-bind:style="{background, style}"
        v-bind:disabled="disabled"
    >
        Click on it
    </button>
</template>

<script>
    export default {
        props: {
            background: {
                type: String,
            },
            background: {
                type: String,
            },
            disabled: {
                type: Boolean,
            },
        }
    }
</script>

<style scoped>
    button:disabled {
        opacity: 0.5;
    }
    button {
        background: none;
        color: black;
        border: none;
        border-radius: 5px;
        padding: 10px 40px;
        font-size: 16px;
        cursor: pointer;
    }
    button:hover{
        filter: brightness(125%);
    }
</style>