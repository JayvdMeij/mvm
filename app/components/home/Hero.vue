<template>
    <section>
        <div class="blob"></div>
        <div class="blob"></div>
        <div class="blob"></div>
        <div class="container">
            <h1>Crafting Digital
                Experiences</h1>
            <p class="text-normal">
                Snelle, toegankelijke websites die gebouwd zijn om te presteren.

Bij Media van Meij draait alles om moderne websites met impact: razendsnel, gebruiksvriendelijk en toekomstbestendig. Van strak design tot slimme techniek, jouw online aanwezigheid werkt voor jou.
            </p>
            <div>
                <baseButton href="/about" variant="white">Learn more</baseButton>
                <baseButton href="/contact" variant="main">Contact us</baseButton>
            </div>
        </div>
    </section>
</template>

<style scoped>
section {
    position: relative;
    height: 90vh;
    overflow: hidden;
    align-content: flex-end;
}

p{
    width: 70%;
    text-wrap: balance;
}

/* Each blob is an absolutely-positioned child element */
section .blob {
    position: absolute;
    border-radius: 50%;
    pointer-events: none;
}

/* Blob 1 — orange-red, top-left */
section .blob:nth-child(1) {
    width: 60vw;
    height: 60vw;
    background: radial-gradient(circle, var(--color1) 0%, transparent 70%);
    top: -15%;
    left: -10%;
    opacity: 0.18;
    filter: blur(120px);
}

/* Blob 2 — purple, right side */
section .blob:nth-child(2) {
    width: 50vw;
    height: 50vw;
    background: radial-gradient(circle, var(--color2) 0%, transparent 70%);
    top: 20%;
    right: -5%;
    opacity: 0.12;
    filter: blur(100px);
}

/* Blob 3 — teal, bottom-center */
section .blob:nth-child(3) {
    width: 40vw;
    height: 40vw;
    background: radial-gradient(circle, var(--color3) 0%, transparent 70%);
    bottom: 0%;
    left: 30%;
    opacity: 0.08;
    filter: blur(140px);
}
</style>