<template>
    <div :class="`${variant}`">
        <h3>{{ title }}</h3>
        <p>{{ description }}</p>
        <ul>
            <li v-for="item in items" :key="item"><img src="~/assets/images/check.svg" alt="check-icon" />{{ item }}
            </li>
        </ul>
        <baseButton href="/contact" :variant="variantBtn" >Kies pakket</baseButton>
    </div>
</template>

<script setup>
defineProps({
    title: { type: String, required: true },
    description: { type: String, required: true },
    items: { type: Array, required: true },
    variantBtn: { type: String, required: true },

    variant:{
        type: String,
        default: 'main',
    }
})
</script>

<style scoped>
    .pakket-card{
        border: 1px red solid;
    }

    .pakket-card-middle{
        border: 3px blue solid;
    }

</style>
