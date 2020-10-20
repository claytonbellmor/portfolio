<template>
  <div class="container">
    <div id="name-container">
      <img id="avatar" src="./../assets/images/profile.jpg" alt="avatar" />
      <h1>Clayton Bellmor</h1>
    </div>
    <div class="title-desc-container">
      <a id="github" href="https://github.com/claytonbellmor">
        <img class="title-font" src="./../assets/images/github.svg" alt="Github" />
        <!-- <img class="title-font" src="./../assets/logos/css.svg" alt="HTML/CSS" /> -->
        <!-- <img class="title-font" src="./../assets/logos/vue.svg" alt="Vue" /> -->
        <!-- <img class="title-font" src="./../assets/logos/ubuntu.svg" alt="Ubuntu" /> -->
        Front End Developer</a
      >
    </div>
    <div class="article">
      <h2>About</h2>
      <p>
        <i>Self-taught front end developer.</i> HTML5/CSS3, Bootstrap, Less, SaSS, Photoshop/Photopea, Figma, Sketch,
        Node, Express, CRUD, APIs, Internet protocols, Vue and React, DevOps, testing, and VSCode and Unix terminals. I
        💚 Github and NPM.<br />
        Twitter: <a href="https://twitter.com/claytonbellmor">@claytonbellmor</a> <br />
        Github: <a href="https://github.com/claytonbellmor">@claytonbellmor</a>
      </p>

      <h2>Interests</h2>
      <ul>
        <li>Full stack web development and automation.</li>
        <li>
          🚗 Passion for fixing code and cars.
        </li>
        <li>🍲 Love for cooking new cuisines.</li>
        <li>🛠️ Hardware and software debugging.</li>
      </ul>

      <h2>Devices</h2>
      <ul>
        <li>MacBook Pro</li>
        <li>MacBook Air with Ubuntu 20</li>
        <li>iPhone SE, iPhone 7, Moto G6</li>
        <li>Dell Optiplex Hackintosh</li>
      </ul>

      <h2>Contacts</h2>
      <ul>
        <li>
          <b>Email：</b>
          <a href="mailto:claytonbellmor@gmail.com">claytonbellmor#gmail.com</a><i> (Preferred)</i>
        </li>
        <li><b>Catch me: </b>Nitch Space in Athens.</li>
      </ul>
    </div>
  </div>
</template>

<style lang="css" scoped>
#name-container {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
}

#avatar {
  width: auto;
  height: 130px;
  border-radius: 10px;
  margin-right: 12px;
}

#copyright:hover {
  border: none;
}

.title-font {
  width: 16px;
  height: 16px;
  margin-right: 4px;
}

.title-desc-container {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin: 8px 0;
}

.title-desc-container a {
  display: flex;
  align-items: center;
}

.title-desc-container span {
  margin: 0px 4px;
}

.title-desc-container #github {
  color: #24292e;
}

.title-desc-container #sspai {
  color: #ca2c2a;
}

.title-desc-container #blog {
  color: #0070f3;
}

a:hover {
  border-bottom: none;
}

h2 {
  font-size: 20px;
  padding: 16px 0 4px 0;
}

ul {
  padding-left: 15px;
  line-height: 30px;
  margin: 0;
}

p {
  line-height: 30px;
}
</style>
