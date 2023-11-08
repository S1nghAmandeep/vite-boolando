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
        }
    },

    mounted() {
        // console.log(this.products);
    }

}

</script>

<template>
    <main>
        <div class="container">
            <div class="row">
                <div class="col--4" v-for="(item, i) in store.products" :key="item.id">
                    <MainCards :items="item" />
                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.col--4 {
    flex-basis: calc((100% / 12) * 4);
}
</style>
