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
}

.footer-row {
    justify-content: space-between;
}

.col-6 {
    flex-basis: calc((100% / 12) * 6);
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
