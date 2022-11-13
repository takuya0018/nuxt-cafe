<template>
  <header class="l-header">
    <p class="l-header-logo">
      <NuxtLink class="l-header-logo__link" to="/">サイト名</NuxtLink>
    </p>
    <nav class="l-header-nav">
      <ul class="l-header-nav__list">
        <li class="l-header-nav__item">
          <NuxtLink class="l-header-nav__link" to="/company/">会社概要</NuxtLink>
        </li>
        <li class="l-header-nav__item">
          <NuxtLink class="l-header-nav__link" to="/info/">新着情報</NuxtLink>
        </li>
      </ul>
    </nav>
  </header>
</template>

<style>
.l-header {
  display: flex;
  padding: 15px;
  background: #333333;
}
.l-header-logo {
  margin: 0;
}
.l-header-logo__link {
  color: #ffffff;
  text-decoration: none;
}
 
.l-header-nav {
  margin-left: auto;
}
.l-header-nav__list {
  display: flex;
  margin: 0;
  padding: 0;
}
.l-header-nav__item {
  list-style: none;
  margin-left: 20px;
}
.l-header-nav__link {
  color: #ffffff;
  text-decoration: none;
}
</style>
