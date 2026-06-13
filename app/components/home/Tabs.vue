<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const sectionPinRef = ref(null)
const sectionRef = ref(null)
const overlayRefs = ref([])

let st = null

onMounted(async () => {
    const { gsap } = await import('gsap')
    const { ScrollTrigger } = await import('gsap/ScrollTrigger')
    gsap.registerPlugin(ScrollTrigger)

    const texts = gsap.utils.toArray('.text-hide')
    const parents = texts.map(t => t.parentElement)
    const overlays = overlayRefs.value
    let currentIndex = 0

    const heights = parents.map(p => p.offsetHeight)

    gsap.set(parents, { height: 0, overflow: 'hidden' })
    gsap.set(texts, { opacity: 0, y: -16 })
    gsap.set(parents[0], { height: heights[0] })
    gsap.set(texts[0], { opacity: 1, y: 0 })
    gsap.set(overlays, { opacity: 0 })
    gsap.set(overlays[0], { opacity: 1 })

    st = ScrollTrigger.create({
        trigger: sectionPinRef.value,
        start: 'top top',
        end: 'bottom bottom',
        pin: sectionRef.value,
        onUpdate: (self) => {
            const newIndex = Math.min(Math.floor(self.progress * 5), 4)
            if (newIndex !== currentIndex) {
                const outText = texts[currentIndex]
                const outParent = parents[currentIndex]
                const inText = texts[newIndex]
                const inParent = parents[newIndex]

                gsap.to(outText, { opacity: 0, y: -16, duration: 0.3, ease: 'power2.in' })
                gsap.to(outParent, { height: 0, duration: 0.3, delay: 0.15, ease: 'power2.in' })

                gsap.set(inText, { y: -16, opacity: 0 })
                gsap.to(inParent, { height: heights[newIndex], duration: 0.35, delay: 0.25, ease: 'power2.out' })
                gsap.to(inText, { opacity: 1, y: 0, duration: 0.35, delay: 0.4, ease: 'power2.out' })

                gsap.to(overlays[currentIndex], { opacity: 0, duration: 0.6 })
                gsap.to(overlays[newIndex], { opacity: 1, duration: 0.6 })

                currentIndex = newIndex
            }
        }
    })
})

onUnmounted(() => {
    st?.kill()
})
</script>

<template>
    <div class="section-pin" ref="sectionPinRef">
        <section ref="sectionRef">
            <div v-for="n in 5" :key="n" :ref="el => { if (el) overlayRefs[n - 1] = el }" class="bg-overlay"
                :class="`bg-overlay-${n}`"></div>
            <div class="container">
                <div>
                    <h2 class="top-head">02 - Services</h2>
                    <h2>what we do</h2>
                    <p>Lorem ipsum dolor sit</p>
                </div>

                <div>
                    <ul>
                        <li>
                            <span>01</span>
                            <div>
                                <h3>Web development</h3>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="lucide lucide-arrow-right text-foreground/60"
                                    aria-hidden="true">
                                    <path d="M5 12h14"></path>
                                    <path d="m12 5 7 7-7 7"></path>
                                </svg>
                            </div>
                            <div>
                                <p class="text-hide text-hide-1">Robuuste en schaalbare websites, gebouwd met moderne
                                    technieken. Van strakke front-ends tot slimme back-ends. Alles is gericht op
                                    gebruiksgemak, onderhoudbaarheid en groei.</p>
                            </div>
                        </li>

                        <li>
                            <span>02</span>
                            <div>
                                <h3>Toegankelijkheid</h3>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="lucide lucide-arrow-right text-foreground/60"
                                    aria-hidden="true">
                                    <path d="M5 12h14"></path>
                                    <path d="m12 5 7 7-7 7"></path>
                                </svg>
                            </div>
                            <div>
                                <p class="text-hide text-hide-2">Een toegankelijke website bereikt meer mensen. Ik bouw
                                    volgens WCAG-richtlijnen zodat iedereen jouw site prettig kan gebruiken, inclusief
                                    en professioneel.</p>
                            </div>
                        </li>

                        <li>
                            <span>03</span>
                            <div>
                                <h3>SEO</h3>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="lucide lucide-arrow-right text-foreground/60"
                                    aria-hidden="true">
                                    <path d="M5 12h14"></path>
                                    <path d="m12 5 7 7-7 7"></path>
                                </svg>
                            </div>
                            <div>
                                <p class="text-hide text-hide-3">Goed gevonden worden begint bij een sterke technische
                                    basis. Ik zorg voor snelle laadtijden, duidelijke structuur en slimme optimalisatie
                                    voor zoekmachines.</p>
                            </div>
                        </li>

                        <li>
                            <span>04</span>
                            <div>
                                <h3>Design</h3>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="lucide lucide-arrow-right text-foreground/60"
                                    aria-hidden="true">
                                    <path d="M5 12h14"></path>
                                    <path d="m12 5 7 7-7 7"></path>
                                </svg>
                            </div>
                            <div>
                                <p class="text-hide text-hide-4">Modern design dat past bij jouw merk. Geen standaard
                                    templates, maar een uitstraling die vertrouwen wekt en bezoekers overtuigt.</p>
                            </div>
                        </li>

                        <li>
                            <span>05</span>
                            <div>
                                <h3>Performance</h3>
                                <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                                    fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" class="lucide lucide-arrow-right text-foreground/60"
                                    aria-hidden="true">
                                    <path d="M5 12h14"></path>
                                    <path d="m12 5 7 7-7 7"></path>
                                </svg>
                            </div>
                            <div>
                                <p class="text-hide text-hide-5">Snelheid maakt het verschil. Een snelle website houdt
                                    bezoekers vast, verhoogt conversies en scoort beter in Google.</p>
                            </div>
                        </li>
                    </ul>
                </div>
            </div>
        </section>
    </div>
</template>

<style scoped>
.section-pin {
    height: 500vh;
}

section {
    position: relative;
    height: 100vh;
}

.bg-overlay {
    position: absolute;
    inset: 0;
    pointer-events: none;
}

.bg-overlay-1 {
    background: linear-gradient(to bottom right, #FF4D1A33, #FF8C691A, transparent);
}

.bg-overlay-2 {
    background: linear-gradient(to bottom right, #6C63FF33, #A09BFF1A, transparent);
}

.bg-overlay-3 {
    background: linear-gradient(to bottom right, #0FA3B133, #5ECBD81A, transparent);
}

.bg-overlay-4 {
    background: linear-gradient(to bottom right, #C8A96E33, #E5C98A1A, transparent);
}

.bg-overlay-5 {
    background: linear-gradient(to bottom right, #2D6A4F33, #52B7881A, transparent);
}

.container {
    position: relative;
    height: 85%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    >div:first-of-type {
        width: 40%;
    }

    >div:last-of-type {
        width: 60%;
    }
}

li {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: var(--gap1);

    span {
        align-content: flex-end;
        grid-column: 1;
        grid-row: 1;
    }

    div:first-of-type {
        grid-column: 2;
        grid-row: 1;
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
    }

    div:last-of-type {
        grid-column: 2;
        grid-row: 2;
        overflow: hidden;
    }
}

ul {
    display: flex;
    flex-direction: column;
    gap: var(--gap2);
}

.text-hide {
    margin-bottom: 0;
    width: 80%;
    text-wrap: balance;
}
</style>
