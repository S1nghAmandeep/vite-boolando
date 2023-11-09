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
            dis: '',
            green: '',
        }
    },
    methods: {
        showModal(products) {
            this.active = true;
            this.items = products
            // this.items.badges.forEach(element => {
            //     this.dis = element.value
            // });
            for (let index = 0; index < this.items.badges.length; index++) {
                const element = this.items.badges[index];
                if (element.type === "tag") {
                    this.green = element.value
                } else {
                    this.dis = element.value
                }

            }
        },
        closeModal() {
            this.active = false;
            this.items = ''
            this.dis = 0
            this.green = ''
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
        <div v-if="active" class="bg-modal">
            <div class="card">
                <div class="card__body">
                    <figure>
                        <img class="imgModal" :src="items.frontImage" alt="">
                    </figure>
                    <div>
                        <p> {{ items.brand }} </p>
                        <p> {{ items.name }} </p>
                        <p> &euro; {{ items.price }} </p>
                        <p> sconto {{ dis }} </p>
                        <p> {{ green }} </p>
                    </div>
                </div>
                <div>
                    <span @click="closeModal">
                        <font-awesome-icon icon="fa-regular fa-circle-xmark" size="xl" />
                    </span>
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.col--4 {
    flex-basis: calc((100% / 12) * 4);
}

.bg-modal::after {
    content: '';
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 1;
    background-color: rgba(0, 0, 0, 0.7);
}

.card {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: white;
    box-shadow: 0px 0px 10px 2px #888888;
    max-width: 800px;
    width: 100%;
    height: 500px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 10px;
    border-radius: 10px;
    z-index: 2;

    .card__body {
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-grow: 1;
        overflow: hidden;
        padding: 10px;
        font-weight: bold;
        gap: 10px;
        font-size: 25px;

        .imgModal {
            display: block;
            width: 300px;
            border-radius: 10px;
            box-shadow: 0px 0px 10px 2px #888888;

        }
    }
}
</style>
