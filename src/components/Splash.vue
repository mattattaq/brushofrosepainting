<script setup>
</script>

<template>
    <section id="splash">
        <div class="container">
            <ul>
                <li class="box rose"></li>
                <li class="box rose-lite"></li>
                <li class="box neutral"></li>
                <li class="box stem-lite"></li>
                <li class="box stem"></li>
            </ul>
        </div>
    </section>
</template>

<style scoped>
ul {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    gap: 10px;
}

li {
    list-style: none;
}

.box {
    width: 100px;
    height: 100px;
    margin-top: 10px;
    border-style: solid;
    border-width: 1px;
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
    margin-top: 50px;
    background-color: var(--rose);
}
</style>
