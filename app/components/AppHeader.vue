<template>
    <header>
        <div class="container">
            <h6>Media van Meij</h6>

            <nav>
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/over-meij">Over Meij</a></li>
                    <li><a href="/contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style scoped>

    header{
        .container{
            display: flex;
            flex-direction: row;
            justify-content: space-between;
            padding-top: 2rem;
            padding-bottom: 2rem;
        }

        nav{
            ul{
                display: flex;
                flex-direction: row;
                gap: 1rem;
            }
        }
    }
</style>