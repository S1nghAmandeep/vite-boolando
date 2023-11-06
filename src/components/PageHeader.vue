<script>

export default {
  data() {
    return {
      category: ['Donna', 'Uomo', 'Bambini']
    }
  }

}

</script>

<template>
  <!-- Barra Navigazione -->
  <header>
    <nav class="container">
      <div class="row nav-row">
        <div class="col-4">
          <ul class="category">
            <li v-for="(item, i9) in category"><a href="#">{{ item }}</a></li>
          </ul>
        </div>
        <div class="col-4"><img class="boolean-logo" src="../assets/boolean-logo.png" alt=""></div>
        <div class="col-4"><img class="header-icon" src="../assets/accedi-img.png" alt=""></div>
      </div>
    </nav>
  </header>
</template>

<style lang="scss" scoped>
@use '../styles/parstials/variables' as *;

header {
  background-color: $header-bg-colour;
  height: 60px;
  width: 100%;
  position: sticky;
  padding-bottom: 50px;
  z-index: 2000;
  top: 0;
}

.nav-row {
  justify-content: space-between;
  padding: 10px;
  align-items: center;
}

.col-4 {
  flex-basis: calc((100% / 12) * 4);
}

ul li {
  color: $white-colour;
  font-weight: bold;
}

.category {
  display: flex;
  gap: 10px;
}

.boolean-logo {
  max-width: 50%;
  margin: 3px 0 0 80px;
}

.header-icon {
  margin: 7px 0 0 214px;
}
</style>
