<script>
// import cards from '../db.json'
import MainCards from '../components/MainCards.vue'
import { store } from '../store'


export default {
    components: {
        MainCards
    },
    data() {
        return {
            store,
            active: false,
            items: '',
        }
    },
    methods: {
        showModal(products) {
            this.active = true;
            this.items = products
        },
        closeModal() {
            this.active = false;
        }
    }

}

</script>

<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col--4" v-for="(item, i) in store.products" :key="item.id">
                    <MainCards @show="showModal" :items="item" />
                </div>
            </div>
        </div>
        <div>
            <div v-if="active" class="card">
                <div class="card__body">
                    <figure>
                        <img class="imgModal" :src="items.frontImage" alt="">
                    </figure>
                    <div>
                        <p> {{ items.brand }} </p>
                        <p> {{ items.name }} </p>
                        <p> &euro; {{ items.price }} </p>
                    </div>
                </div>
                <div>
                    <span @click="closeModal"><font-awesome-icon icon="fa-regular fa-circle-xmark" /></span>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.col--4 {
    flex-basis: calc((100% / 12) * 4);
}

.card {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%);
    background-color: white;
    box-shadow: 0px 0px 10px 2px #888888;
    max-width: 450px;
    width: 100%;
    height: 200px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 10px;
    align-items: center;
    border-radius: 10px;

    .card__body {
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-grow: 1;
        overflow: hidden;
        padding: 10px;
        font-weight: bold;
        gap: 10px;

        .imgModal {
            display: block;
            width: 100px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px 2px #888888;

        }
    }
}
</style>
