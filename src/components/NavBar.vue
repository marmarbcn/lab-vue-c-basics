<template>
    <div id="navbar">
        <h1>This is a navbar component</h1>
        <div class="menu">
            <button class="btn-menu" @click="alertMsg">Iteration 2</button>
            <button class="btn-menu">Iteration 3</button>
            <button class="btn-menu" @click="alertMessage()">Iteration 4</button>
            <button class="btn-menu">Iteration 5</button>
        </div>

    </div>
</template>

<script>

const message = "Hey! Esto no va!"
function alertMessage() {
    console.log(message)
}

</script>

<style scoped>
#navbar {
    background-color: #FF00FF;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    border-bottom: 5px solid black;
    padding: 0 40px;
}

h1 {
    color: black;
}

.btn-menu {
    background-color: aquamarine;
    border: 5px solid black;
    padding: 10px;
    margin: 0 5px;
}
</style>