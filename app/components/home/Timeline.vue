<template>
    <section>
        <div class="container">
            <h2>Welcome texts</h2>
            <p>
                homepage
            </p>
            <div class="grid">
                <div class="left"></div>
                <div class="middle">
                    <div class="circle"></div>
                </div>
                <div class="right">
                    <img src="~/assets/images/check.svg" alt="filler">
                    <h3>Kennismaking</h3>
                    <p>We bespreken jouw wensen, doelen en ideeën.</p>
                </div>

                <div class="left">
                    
                    <img src="~/assets/images/check.svg" alt="filler">
                    <h3>Kennismaking</h3>
                    <p>We bespreken jouw wensen, doelen en ideeën.</p>
                    
                </div>
                <div class="middle">
                    <div class="circle"></div>
                </div>
                <div class="right"></div>

                <div class="left"></div>
                <div class="middle">
                    <div class="circle"></div>
                </div>
                <div class="right">
                    <img src="~/assets/images/check.svg" alt="filler">
                    <h3>Kennismaking</h3>
                    <p>We bespreken jouw wensen, doelen en ideeën.</p>
                </div>

                <div class="left">
                    
                    <img src="~/assets/images/check.svg" alt="filler">
                    <h3>Kennismaking</h3>
                    <p>We bespreken jouw wensen, doelen en ideeën.</p>
                    
                </div>
                <div class="middle">
                    <div class="circle"></div>
                </div>
                <div class="right"></div>

                <div class="left"></div>
                <div class="middle">
                    <div class="circle"></div>
                </div>
                <div class="right">
                    <img src="~/assets/images/check.svg" alt="filler">
                    <h3>Kennismaking</h3>
                    <p>We bespreken jouw wensen, doelen en ideeën.</p>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
.grid{
    display: grid;
    grid-template-columns: 1fr 60px 1fr;
}

.left, .middle, .right{
    display: flex;
    flex-direction: column;
}

.left{
    align-items: start;
}

.middle{
    justify-content: center;
    align-items: center;
}

.right{
    align-items: end;
}


.circle{
    height: 20px;
    width: 20px;
    border: 2px solid var(--donker-blauw);
    border-radius: 99px;
}
</style>