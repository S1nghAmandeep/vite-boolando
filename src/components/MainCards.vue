<script>
export default {
    props: {
        items: {
            type: Object,
            required: true
        }
    },
    methods: {
        getImagePath(imgPath) {
            return new URL(imgPath, import.meta.url).href;
        },

        // getDiscount(price, discount) {

        //     let disNum
        //     for (let index = 0; index < discount.length; index++) {
        //         const element = discount[index]
        //         // console.log(element);
        //         if (element.type === 'discount') {
        //             disNum = element.value
        //         }
        //     }
        //     console.log(disNum);

        //     const finalPrice = ((price * parseInt(disNum)) / 100) * -1
        //     // console.log(finalPrice);
        //     return finalPrice.toFixed(2)
        // }

    }
}
</script>

<template>
    <div class="card-1">
        <img class="top-image" :src="getImagePath(`../assets/${items.backImage}`)" alt="">
        <img class="clothe-image" :src="items.frontImage" alt="t-shirt">
        <p class="brand">{{ items.brand }}</p>
        <strong @click="$emit('show', items)">
            {{ items.name }}
        </strong>
        <span class="price">&euro;
            {{ items.price }}
        </span>
        <!-- <span class="old-price">
            {{ items.price }}
        </span> -->
        <div class="discount">
            <span v-for="(dis, index) in items.badges" :key="index"
                :class="dis.value === 'Sostenibilità' ? 'sustainable' : 'bg-red'">
                {{ dis.value }}
            </span>
        </div>
        <div class="red">
            <span :class="items.isInFavorites ? 'heart-red' : 'heart'">&hearts;</span>
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
    color: $white-colour;
    font-weight: bold;
    position: absolute;
    left: 0;
    bottom: 100px;
    display: flex;
    flex-direction: row-reverse;
    align-items: center;

    .sustainable {
        background-color: $green-colour;
        color: $white-colour;
        padding: 5px 10px;
    }

    .bg-red {
        background-color: $red-colour;
        color: $white-colour;
        padding: 5px 10px;
    }
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
}

strong {
    display: block;
}
</style>