<template>
    <div class="image">
        <img :src="src" :alt="alt">
    </div>
</template>

<script>
export default {
    name: 'Result',
    props: {
        src: String,
        alt: String,
    }
}
</script>

<style lang="scss">
    .image {
        width: 100%;
        display: flex;
        img {
            justify-content: center;
            align-items: center;
        }
    }
</style>