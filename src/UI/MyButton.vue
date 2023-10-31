<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>

</script>

<style>
    .btn {
        width: 100px;
        align-self: flex-end;
        height: 30px;
        background-color: aliceblue;
        border: 2px solid rgb(116, 116, 209);
    }
</style>