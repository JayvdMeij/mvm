<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const trackRef = ref(null)
const ulRef = ref(null)
let anim = null

onMounted(async () => {
    const { gsap } = await import('gsap')
    const track = trackRef.value
    const firstUl = ulRef.value
    const ulWidth = firstUl.offsetWidth

    while (track.scrollWidth < window.innerWidth * 2) {
        const clone = firstUl.cloneNode(true)
        clone.setAttribute('aria-hidden', 'true')
        track.appendChild(clone)
    }

    anim = gsap.fromTo(
        track,
        { x: 0 },
        { x: -ulWidth, duration: 10, ease: 'none', repeat: -1 }
    )
})

onUnmounted(() => {
    anim?.kill()
})
</script>

<template>
    <section>
        <div class="container">
            <div class="track" ref="trackRef">
                <ul ref="ulRef">
                    <li>Item 1</li>
                    <li>Item 2</li>
                    <li>Item 3</li>
                    <li>Item 4</li>
                    <li>Item 5</li>
                    <li>Item 6</li>
                </ul>
            </div>
        </div>
    </section>
</template>

<style scoped>
.container {
    padding-top: 2rem;
    padding-bottom: 2rem;
    overflow: hidden;
}

.track {
    display: flex;
    will-change: transform;
}

ul {
    display: flex;
    flex-direction: row;
    gap: var(--gap3);
    padding-right: var(--gap3);
    flex-shrink: 0;
}

li {
    white-space: nowrap;
}
</style>
