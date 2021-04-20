<template>
  <div id="header-top">
    <div id="header-logo">
      <NuxtLink exact to="/">
        <img
          alt="Safest Betting Sites"
          src="https://sbs.test/wp-content/themes/SafestBettingSites/images/sbs_logo_basketball.png"
          data-src="https://sbs.test/wp-content/themes/SafestBettingSites/images/sbs_logo_basketball.png"
        />
      </NuxtLink>
    </div>
    <div id="header-desc">
      Your Guide to the<span>Safest Betting Sites</span>
    </div>
  </div>
</template>

<style lang="scss" scoped>
#header-top {
  height: 103px;
  padding: 20px 0px 0px 0px;
}

#header-logo {
  float: left;
  margin-right: 20px;
  padding-right: 20px;
  border-right: solid 1px #43668d;
}
#header-desc {
  float: left;
  color: $white;
  font-family: $font-title;
  font-size: 14px;
  text-transform: uppercase;

  span {
    display: block;
    color: #29d9b9;
  }
}

ul {
  padding-left: 0;

  li {
    display: inline-block;
    margin-right: 30px;
  }
}
</style>
