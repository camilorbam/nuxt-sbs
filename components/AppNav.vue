<template>
  <nav class="main-nav header-nav">
    <ul>
      <li>
        <NuxtLink exact to="/">SBS </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/">About</NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<style lang="scss" scoped>
.main-nav {
  position: relative;
}

.header-nav {
  clear: both;

  li {
    list-style: none;
  }
  > ul {
    display: table;
    margin: 0 auto;
  }
  > ul > li {
    position: relative;
    display: table-cell;
    padding: 0px 4px 0px 0px;
    vertical-align: top;
  }
  > ul > li:last-of-type {
    padding-right: 0;
  }
  > ul > li > a {
    display: block;
    padding: 9px 14px;
    color: $white;
    background: $primary;
    background: linear-gradient(to bottom, $primary 0%, $blue-500 100%);
    font-family: 'Roboto Condensed', Arial Narrow, Arial, sans-serif;
    font-size: 15px;
    text-decoration: none;
    text-transform: uppercase;
    border-radius: 3px 3px 0 0;
    cursor: pointer;
    user-select: none;
  }
  > ul > li > a:hover,
  a.search-icon:hover {
    color: $blue-500;
    background: #eff3f3;
    background: linear-gradient(to bottom, #eff3f3 0%, #bec4c8 100%);
  }
  > ul > li:hover > ul {
    display: block;
  }
  ul.sub-menu {
    display: none;
    position: absolute;
    z-index: 99999;
    top: 42px;
    left: 0;
    width: 200px;
    border-right: solid 1px $wb-350;
    border-bottom: solid 1px $wb-350;
    border-left: solid 1px $wb-350;
  }
  ul.sub-menu li {
    min-width: 180px;
  }
  ul.sub-menu ul {
    top: 0;
    left: 100%;
  }
  ul.sub-menu a {
    display: block;
    position: relative;
    padding: 10px 5px 10px 20px;
    border-bottom: solid 1px #eceff1;
    color: $wb-800;
    background: $white;
    font-size: 13px;
    text-decoration: none;
  }

  ul.sub-menu a:hover {
    color: $blue-600;
    background: #f0f6ff;
  }

  > ul > li.featured-tab > a {
    color: #1890cc;
    background: linear-gradient(to bottom, #fefefe 50%, $wb-350 100%);
  }
  > ul > li.featured-tab.style2 > a {
    color: $white;
    background: linear-gradient(to bottom, #c0262d 50%, #b10608 100%);
  }
  > ul > li.featured-tab > a:hover {
    color: $blue-500;
    background: #eff3f3;
    background: linear-gradient(to bottom, #eff3f3 0%, #bec4c8 100%);
  }
}

div {
  align-items: center;
  display: flex;
  height: 100%;
  width: 100%;
}

ul {
  padding-left: 0;

  li {
    display: inline-block;
    margin-right: 30px;
  }
}
</style>
