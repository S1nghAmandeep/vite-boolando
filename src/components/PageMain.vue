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
        }
    },
    methods: {
        showModal() {
            this.active = true;
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
                <p>ciao come stai</p>
                <span @click="closeModal"><font-awesome-icon icon="fa-regular fa-circle-xmark" /></span>
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
    transform: translate(-50% -50%);
    background-color: white;
    box-shadow: 0px 0px 10px 2px #888888;
    max-width: 300px;
    width: 100%;
    height: 80px;
    display: flex;
    justify-content: space-around;
    align-items: center;
    border-radius: 10px;
}
</style>
