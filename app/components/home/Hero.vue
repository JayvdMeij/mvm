<template>
    <section>
        <div class="container">
            <h1>Welcome texts</h1>
            <p class="text-normal">
                homepage
            </p>
            <div>
            <buttonMain href="/about">Learn more</buttonMain>
            <buttonWhite href="/contact">Contact us</buttonWhite>
            </div>
        </div>
    </section>
</template>

<style scoped>
section {
    background-image: radial-gradient(ellipse farthest-side at center, rgba(199, 210, 254, 0.4), rgba(233, 213, 255, 0.4), #fafafc 90%);
    height: 70vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    
}
</style>