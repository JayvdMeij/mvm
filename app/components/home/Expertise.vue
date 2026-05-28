<script setup>
import { ref } from 'vue'

const activeTab = ref(0)

const tabs = [
    {
        title: 'Web development',
        icon: '',
        heading: 'Heading here',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
        link: '#',
        linkLabel: 'Meer lezen'
    },
    {
        title: 'Toegankelijkheid',
        icon: '',
        heading: 'Heading here',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
        link: '#',
        linkLabel: 'Meer lezen'
    },
    {
        title: 'SEO',
        icon: '',
        heading: 'Heading here',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
        link: '#',
        linkLabel: 'Meer lezen'
    },
    {
        title: 'Design',
        icon: '',
        heading: 'Heading here',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
        link: '#',
        linkLabel: 'Meer lezen'
    },
    {
        title: 'Performance',
        icon: '',
        heading: 'Heading here',
        text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit.',
        link: '#',
        linkLabel: 'Meer lezen'
    },
]
</script>

<template>
    <section class="expertise">
        <div class="container">
            <div class="expertise__tabs">
                <nav class="expertise__nav">
                    <button
                        v-for="(tab, index) in tabs"
                        :key="index"
                        class="expertise__tab"
                        :class="{ 'expertise__tab--active': activeTab === index }"
                        @click="activeTab = index"
                    >
                        {{ tab.title }}
                    </button>
                </nav>

                <div class="expertise__content">
                    <span class="expertise__icon">{{ tabs[activeTab].icon }}</span>
                    <h3>{{ tabs[activeTab].heading }}</h3>
                    <p>{{ tabs[activeTab].text }}</p>
                    <a :href="tabs[activeTab].link">{{ tabs[activeTab].linkLabel }}</a>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.expertise__tabs {
    display: flex;
    gap: 4rem;
}

.expertise__nav {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    min-width: 200px;
}

.expertise__tab {
    background: none;
    border: none;
    text-align: left;
    padding: 0.75rem 1rem;
    cursor: pointer;
    font-family: var(--font-main), sans-serif;
    font-size: var(--font-size-textnormal);
    color: var(--text-kleur);
    border-radius: 6px;
}

.expertise__tab--active {
    color: var(--donker-blauw);
    font-weight: 600;
    background: var(--off-white-grijs);
}

.expertise__content {
    flex: 1;
}
</style>
