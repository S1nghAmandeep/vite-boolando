<script>

export default {
    data() {
        return {

        }
    }

}



</script>

<template>
    <footer>
        <div class="container footer-border">
            <div class="row footer-row">
                <div class="col-6">
                    <div class="footer-text">
                        <strong>Boolando s.r.l</strong>
                        <p>informazioni legali informativa sulla privacy Diritto di recesso</p>
                    </div>
                </div>
                <div class="col-6">
                    <div class="footer-text-2">
                        <p>Trovaci anche su</p>
                        <img src="../assets/Senza titolo-1.png" alt="">
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
@use '../styles/parstials/variables' as *;

footer {
    background-color: $footer-bg-colour;
    height: 110px;
    width: 100%;
    /* position: sticky;
    z-index: 2000;
    bottom: 0;*/
}

.footer-row {
    justify-content: space-between;
}

.col-6 {
    flex-basis: calc((100% / 12) * 6);
    /* flex-basis: calc((100% * 2) / 12); */
    /* border: 1px dashed black; */
}

.footer-border {
    padding-top: 20px;
}

.footer-text {
    color: $white-colour;
    line-height: 25px;
}

.footer-text-2 {
    color: $white-colour;
    line-height: 25px;
    text-align: right;
}
</style>
