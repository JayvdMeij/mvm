<template>
    <section>
        <div class="container">
            <div>
                <div>
                    <h2>03- Work</h2>
                    <p>Een kijkje in mijn werk</p>
                </div>
                <div>
                    <a href="/projecten">Lees meer -></a>
                </div>
            </div>
            <div class="grid">
                <div class="card project-1">
                    <img src="../assets/images/check.svg" alt="img">
                    <p>Website</p>
                    <h3>Raamfolie</h3>
                    <div>
                        <p>tag1</p>
                        <p>tag1</p>
                    </div>
                </div>

                <div class="card-big project-2">
                    <p>Website</p>
                    <h3>Raamfolie</h3>
                </div>

                <div class="card-big project-3">
                    <p>Website</p>
                    <h3>Raamfolie</h3>
                </div>

                <div class="card project-4">
                    <p>Website</p>
                    <h3>Raamfolie</h3>
                </div>
            </div>

        </div>
    </section>
</template>

<style scoped>
.grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--gap2);
}

.card, .card-big{
    display: flex;
    flex-direction: column;
    gap: var(--gap1);
    height: 20rem;
    border-radius: var(--border-radius);
    padding: 2rem;
    background: #00000057;
    background-position: center center;
    background-size: cover;

    h3{
        color: var(--wit);
    }
}


.card {
    grid-column: span 1;
}

.card-big {
    grid-column: span 2;
}

.project-1 {
    background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('~/assets/images/raamfolie.avif');
}

.project-2 {
    background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('~/assets/images/raamfolie.avif');
}

.project-3 {
    background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('~/assets/images/raamfolie.avif');
}

.project-4 {
    background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('~/assets/images/raamfolie.avif');
}
</style>