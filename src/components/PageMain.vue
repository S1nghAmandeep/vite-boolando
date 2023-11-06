<script>

export default {
    data() {
        return {

        }
    }

}

</script>

<template>
    <main>
        <div>
            <div class="container">
                <div class="row">

                    <!-- card immagine 1 -->

                    <div class="col--4">
                        <div class="card-1">
                            <img class="top-image" src="../assets/1b.webp" alt="">
                            <img class="clothe-image" src="../assets/1.webp" alt="t-shirt">
                            <p class="brand">Levi's</p>
                            <strong>RELEXED FIT TEE UNISEX</strong>
                            <span class="price">14,99 &euro; </span>
                            <span class="old-price">29,99 euro</span>
                            <span class="discount">-50%</span>
                            <span class="sustainable">Sostenibilità</span>
                            <div class="red">
                                <span class="heart">&hearts;</span>
                                <span class="heart-red">&hearts;</span>
                            </div>

                        </div>
                    </div>

                    <!-- card immagine 2 -->

                    <div class="col--4">
                        <div class="card-1">
                            <img class="top-image" src="../assets/2b.webp" alt="">
                            <img class="clothe-image" src="../assets/2.webp" alt="t-shirt">
                            <p class="brand">Guess</p>
                            <strong>ROSES TEE</strong>
                            <span class="price">20,99 &euro; </span>
                            <span class="old-price">29,99 euro</span>
                            <span class="discount">-30%</span>
                            <div class="red">
                                <span class="heart">&hearts;</span>
                                <span class="heart-red">&hearts;</span>
                            </div>
                        </div>
                    </div>

                    <!-- card immagine 3 -->

                    <div class="col--4">
                        <div class="card-1">
                            <img class="top-image" src="../assets/3b.webp" alt="">
                            <img class="clothe-image" src="../assets/3.webp" alt="t-shirt">
                            <p class="brand">Come Zueccher Filato</p>
                            <strong>VOGLIO DI COLORI PASTELLO</strong>
                            <span class="price">129,99 &euro; </span>
                            <span class="old-price">184,99 euro</span>
                            <span class="discount">-30%</span>
                            <div class="red">
                                <span class="heart">&hearts;</span>
                                <span class="heart-red">&hearts;</span>
                            </div>
                        </div>
                    </div>

                    <!-- card immagine 4 -->

                    <div class="col--4">
                        <div class="card-1">
                            <img class="top-image" src="../assets/4b.webp" alt="">
                            <img class="clothe-image" src="../assets/4.webp" alt="t-shirt">
                            <p class="brand">Levi's</p>
                            <strong>TEE UNISEX</strong>
                            <span class="price">14,99 &euro; </span>
                            <span class="old-price">29,99 euro</span>
                            <span class="discount">-50%</span>
                            <div class="red">
                                <span class="heart">&hearts;</span>
                                <span class="heart-red">&hearts;</span>
                            </div>
                            <span class="sustainable">Sostenibilità</span>
                        </div>
                    </div>

                    <!-- card immagine 5 -->

                    <div class="col--4">
                        <div class="card-1">
                            <img class="top-image" src="../assets/5b.webp" alt="">
                            <img class="clothe-image" src="../assets/5.webp" alt="t-shirt">
                            <p class="brand">Maya Deluxe</p>
                            <strong>STRIPE BODICE</strong>
                            <span class="price">99,99 &euro; </span>
                            <div class="red">
                                <span class="heart">&hearts;</span>
                                <span class="heart-red">&hearts;</span>
                            </div>

                        </div>
                    </div>

                    <!-- card immagine 6 -->

                    <div class="col--4">
                        <div class="card-1">
                            <img class="top-image" src="../assets/6b.webp" alt="">
                            <img class="clothe-image" src="../assets/6.webp" alt="t-shirt">
                            <p class="brand">Esprit</p>
                            <strong>MAGLIONE - BLACK</strong>
                            <span class="price">29,99 &euro; </span>
                            <div class="red">
                                <span class="heart">&hearts;</span>
                                <span class="heart-red">&hearts;</span>
                            </div>
                            <span class="sustainable six">Sostenibilità</span>
                        </div>
                    </div>

                </div>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
.col--4 {
    flex-basis: calc((100% / 12) * 4);
    /* border: 1px dashed black; */
}

.top-image {
    position: absolute;
    opacity: 0;
    transition: opacity 1s;
}

.card-1:hover .top-image {
    opacity: 1;
}

.card-1 {
    position: relative;
}

.brand {
    color: rgb(146, 146, 146);
}

.price {
    color: red;
    display: inline-block;
    font-weight: bold;
}

.old-price {
    text-decoration: line-through;
}

.discount {
    background-color: red;
    color: white;
    padding: 5px 10px;
    font-weight: bold;
    position: absolute;
    left: 0;
    bottom: 100px;
}

.sustainable {
    background-color: green;
    color: white;
    padding: 5px 10px;
    font-weight: bold;
    position: absolute;
    left: 60px;
    bottom: 100px;
}

.heart {
    padding: 5px 14px;
    font-size: 30px;
    background-color: white;
    position: absolute;
    right: 0;
    top: 10px;
}

.heart-red {
    padding: 5px 14px;
    font-size: 30px;
    background-color: white;
    position: absolute;
    color: red;
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
