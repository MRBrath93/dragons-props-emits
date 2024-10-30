<script setup>
const props = defineProps({
    dragon:Object,
});


// Destructuring - nemmere at sætte indhold ind fra object.
const {name, Skills, img_url} = props.dragon;

const model = defineModel();


</script>



<template>
    <article>
        <h2 class="name">{{props.dragon.name}}</h2>
        <img :src="img_url" :alt="name">
        <p class="skills">{{Skills}}</p>
        <form>
            <label for="betterName">Rename to:</label>
            <input v-model="model" type="text" placeholder="Better name..." id="betterName" required>
            <input type="submit" value="Update name" />
        </form>
    </article>
</template>

<style scoped>
article{
    box-shadow: 0 0 3px 1px rgb(0, 0, 0, .2);
    border-radius: 6px;
    padding: 10px;
}

img{
    width: 100%;
}
</style>