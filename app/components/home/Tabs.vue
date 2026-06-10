<template>
    <section>
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
                            <h3>Brand Identity</h3>
                            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24"
                                fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round" class="lucide lucide-arrow-right text-foreground/60"
                                aria-hidden="true">
                                <path d="M5 12h14"></path>
                                <path d="m12 5 7 7-7 7"></path>
                            </svg>
                        </div>
                        <div>
                            <p>Logos, typography, colour, and all the marks that make a brand unmistakable.</p>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </section>
</template>

<style scoped>


.container{
    height: 100vh;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    background-image: linear-gradient(to bottom right, var(--color1), var(--color1-5), transparent);

    div:nth-first-of-type{
        width: 30%;
    }

    div:nth-last-of-type{
        width: 50%;
    }
}

li{
    display: grid;
    grid-template-columns: auto 1fr;
    gap: var(--gap1);

    span {
        align-content: flex-end;

        grid-column: 1;
        grid-row: 1;
    }

    div:first-of-type{
        grid-column: 2;
        grid-row: 1;
        display: flex;
        justify-content: space-between;
        align-items: flex-end;
    }

    div:last-of-type{
        grid-column: 2;
        grid-row: 2;
    }

}



</style>