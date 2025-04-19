<script setup>
</script>

<template>
    <section id="splash">
        <div class="container">
            <div class="half"></div>
            <div class="half text-center">
                <h1>Lorem ipsum is placeholder text commonly used in the graphic, print, and publishing industries for
                    previewing layouts and visual mockups.</h1>
                <span>- Michael Scott</span>
            </div>
        </div>
        <ul>
            <li class="box rose"></li>
            <li class="box rose-lite"></li>
            <li class="box neutral"></li>
            <li class="box stem-lite"></li>
            <li class="box stem"></li>
        </ul>
    </section>
</template>

<style scoped>
ul {
    display: grid;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 10px;
}

li {
    list-style: none;
}

h1 {
    width: 100%;
    display: block;
}

.box {
    width: 100px;
    height: 100px;
    border-style: solid;
    border-width: 1px;
}

.text-center {
    text-align: center;
    align-items: center;
}

.box.rose {
    background-color: var(--rose);
}

.box.rose-lite {
    background-color: var(--rose-lite);
}

.box.neutral {
    background-color: var(--neutral);
}

.box.stem-lite {
    background-color: var(--stem-lite);
}

.box.stem {
    background-color: var(--stem);
}

#splash {
    background-color: var(--rose);
}
</style>
