<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name: 'my-button',
    }
</script>

<style>
    .btn {
        width: 100px;
        align-self: flex-end;
        height: 30px;
        background-color: aliceblue;
        border: 2px solid rgb(116, 116, 209);
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>