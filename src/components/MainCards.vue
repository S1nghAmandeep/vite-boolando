<script>
export default {
    props: {
        items: {
            type: Object,
        }
    }
}
</script>

<template>
    <div class="card-1">
        <img class="top-image" :src="items.backImage" alt="">
        <img class="clothe-image" :src="items.frontImage" alt="t-shirt">
        <p class="brand">{{ items.brand }}</p>
        <strong>{{ items.name }}</strong>
        <span class="price"> &euro;{{ items.price }}</span>
        <span v-for="dis in items.badges" class="discount">{{ dis.value }}</span>
        <span class="sustainable">Sostenibilità</span>
        <div class="red">
            <span class="heart">&hearts;</span>
            <span class="heart-red">&hearts;</span>
        </div>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/parstials/variables' as *;



.top-image {
    position: absolute;
    opacity: 0;
    transition: opacity 1s;
}

.card-1 {
    position: relative;

    &:hover .top-image {
        opacity: 1;
    }
}

.brand {
    color: $brand-colour;

}

.price {
    color: $red-colour;
    display: inline-block;
    font-weight: bold;
}

.old-price {
    text-decoration: line-through;
}

.discount {
    background-color: $red-colour;
    color: $white-colour;
    padding: 5px 10px;
    font-weight: bold;
    position: absolute;
    left: 0;
    bottom: 100px;
}

.sustainable {
    background-color: $green-colour;
    color: $white-colour;
    padding: 5px 10px;
    font-weight: bold;
    position: absolute;
    left: 60px;
    bottom: 100px;
}

.heart {
    padding: 5px 14px;
    font-size: 30px;
    background-color: $white-colour;
    position: absolute;
    right: 0;
    top: 10px;
}

.heart-red {
    padding: 5px 14px;
    font-size: 30px;
    background-color: $white-colour;
    position: absolute;
    color: $red-colour;
    right: 0;
    top: 10px;
    opacity: 0;
}

.red:hover .heart-red {
    opacity: 1;
    transition: opacity 500ms;
}

strong {
    display: block;
}

.sustainable.six {
    left: 0px;
}
</style>