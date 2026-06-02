<template>
    <section>
        <div class="container">
            <div>
                <h2>Resulaten in cijfers</h2>
                <p>Wat we hebben bereikt</p>
            </div>
            
            <div class="grid">
                <div class="card">
                    <h3>Projecten</h3>
                    <h4>50+</h4>
                    <div class="line"></div>
                    <p>Succesvolle websites opgeleverd voor bedrijven en organisaties.</p>
                </div>

                <div class="card">
                    <img src="~/assets/images/check.svg" alt="filler">
                    </div>

                <div class="card">
                    <h3>Projecten</h3>
                    <h4>50+</h4>
                    <div class="line"></div>
                    <p>Succesvolle websites opgeleverd voor bedrijven en organisaties.</p>
                </div>

                <div class="card">
                    <h3>Projecten</h3>
                    <h4>50+</h4>
                    <div class="line"></div>
                    <p>Succesvolle websites opgeleverd voor bedrijven en organisaties.</p>
                </div>

                <div class="card-large">
                    <img src="~/assets/images/check.svg" alt="filler">
                    </div>
            </div>

            
        </div>
    </section>
</template>

<style scoped>
.container > div:first-of-type{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
    
}

.grid{
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: var(--gap2);
}

.card{
    grid-column: span 1;
    background-color: var(--wit);
    padding: 2rem;
    border: var(--border);
    border-radius: var(--border-radius);
    display: flex;
    flex-direction: column;
    gap: var(--gap1);

    h4{
        align-self: end;
    }

    p{
        font-size: var(--font-size-textbig);
    }
}

.card-large{
        grid-column: span 2;

    background-color: var(--wit);
    padding: 2rem;
    border: var(--border);
    border-radius: var(--border-radius);
    }

    .line{
        width: 100%;
        height: 1px;
        background-color: var(--off-white-grijs);

    }

</style>