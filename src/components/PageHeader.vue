<script>

export default {
  data() {
    return {
      category: ['Donna', 'Uomo', 'Bambini'],
      icons: [['far', 'user'], ['far', 'heart'], ['fas', 'bag-shopping']]
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
            <li v-for="(item, i) in category"><a href="#">{{ item }}</a></li>
          </ul>
        </div>
        <div class="col-4"><img class="boolean-logo" src="../assets/boolean-logo.png" alt=""></div>
        <div class="col-4">
          <ul class="icons">
            <li v-for="(icon, i) in icons">
              <font-awesome-icon :icon="icon" bounce />
            </li>
          </ul>
        </div>
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

.icons {
  display: flex;
  justify-content: flex-end;
  gap: 10px
}
</style>
