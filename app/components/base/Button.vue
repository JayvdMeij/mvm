<template>
    <a :href="href" :class="`btn--${variant}`">
        <slot />
    </a>
</template>

<script setup>
defineProps({
    href: {
        type: String,
        required: true,
    },

    variant: {
        type: String,
        default: 'main',
    }
})
</script>


<style scoped>
a {
    display: inline-block;

    background-color: var(--wit);
    padding: 10px 30px;
    transition: transform 0.2s ease-in-out;
    border-radius: 400px;

    &:hover {
        transform: translateY(-3px);
    }
}

    .btn--main {
        background-color: transparent;
        border: var(--border);
    }

    .btn--white {

    }

</style>