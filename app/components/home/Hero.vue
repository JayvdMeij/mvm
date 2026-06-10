<template>
    <section>
        <div class="blob"></div>
  <div class="blob"></div>
  <div class="blob"></div>
        <div class="container">
            <h1>Welcome texts</h1>
            <p class="text-normal">
                homepage
            </p>
            <div>
                <baseButton href="/about" variant="main">Learn more</baseButton>
                <baseButton href="/contact" variant="white">Contact us</baseButton>
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
    background: radial-gradient(circle, #FF4D1A 0%, transparent 70%);
    top: -15%;
    left: -10%;
    opacity: 0.18;
    filter: blur(120px);
}

/* Blob 2 — purple, right side */
section .blob:nth-child(2) {
    width: 50vw;
    height: 50vw;
    background: radial-gradient(circle, #6C63FF 0%, transparent 70%);
    top: 20%;
    right: -5%;
    opacity: 0.12;
    filter: blur(100px);
}

/* Blob 3 — teal, bottom-center */
section .blob:nth-child(3) {
    width: 40vw;
    height: 40vw;
    background: radial-gradient(circle, #0FA3B1 0%, transparent 70%);
    bottom: 0%;
    left: 30%;
    opacity: 0.08;
    filter: blur(140px);
}
</style>