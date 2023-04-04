<template>
    <p>
    <p class="p-instructions">Display a list of elements that are stored inside a component:</p>
    </p>
    <div id="films">
        <ul>
            <li><span>Title: </span>{{ title }}</li>
            <li><span>Director: </span>{{ description }}</li>
            <li><span>Resume: </span>{{ content }}</li>
        </ul>
    </div>
</template>

<script setup>


const props = defineProps(['title', 'description', 'content']);

</script>
<style scoped>
span {
    font-weight: 700;
}

ul {
    border-bottom: 3px dotted black;
}

li:last-child {
    margin-bottom: 20px;
}
</style>