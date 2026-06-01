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

    color: var(--donker-blauw);
    background-color: var(--wit);
    padding: 10px 30px;
    transition: transform 0.2s ease-in-out;
    border-radius: 400px;

    &:hover {
        transform: translateY(-3px);
    }
}

    .btn--main {
        color: var(--off-white-wit);
        background-color: var(--donker-blauw);
    }

    .btn--white {
        color: var(--donker-blauw);
        background-color: var(--wit);
    }

</style>