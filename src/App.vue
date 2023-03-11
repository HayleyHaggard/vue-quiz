<template>
  <div class="container">
    <RouterView />
  </div>
</template>

<script></script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Tilt+Neon&display=swap");

.container {
  font-family: "Tilt Neon", cursive;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 15px;
}

html {
  box-sizing: border-box;
}

*,
*::after,
*::before {
  box-sizing: inherit;
}

ul[class],
ol[class] {
  padding: 0;
}

body,
h1,
h2,
h3,
h4,
h5,
h6,
p,
ul,
ol,
li,
figure,
figcaption,
blockquote,
dl,
dd {
  margin: 0;
}

ul[class] {
  list-style: none;
}

img {
  max-width: 100%;
  display: block;
}

input,
button,
textarea,
select {
  font: inherit;
}

a {
  text-decoration: none;
}
</style>
