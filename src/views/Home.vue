<template>
  <div class="container">
    <div id="name-container">
      <img id="avatar" src="./../assets/images/av.png" alt="avatar" />
      <h1>skyrocketing Hong</h1>
    </div>
    <div class="title-desc-container">
      <a id="github" href="https://github.com/skyrocketingHong" target="_blank" rel="noopener noreferrer"
        ><img class="title-font" src="./../assets/images/github.svg" />Developer</a
      >
      <span> | </span>
      <a id="blog" href="https://blog.skyrocketing.ninja/" target="_blank" rel="noopener noreferrer"
        ><img class="title-font" src="./../assets/images/wordpress.svg" />Blogger</a
      >
    </div>
    <div class="article">
      <h2>WHO AM I</h2>
      <p>
        I'm <i>skyrocketing Hong</i> with the ID <i>skyrocketingHong</i>.
      </p>

      <h2>Academics</h2>
      <ul>
        <li>
          🏫 Fresh graduate at 🇨🇳
          <a href="http://www.ctgu.edu.cn/" target="_blank" rel="noopener noreferrer">China Three Gorges University</a
          >, <i>BSc in Computer Science</i>.
        </li>
      </ul>

      <h2>Devices</h2>
      <ul>
        <li>⚫ OMEN by HP 15-ce000 Laptop</li>
        <li>⚫ iPhone XR / iPhone 5s / iPad 6 / AirPods / Beats Flex</li>
      </ul>

      <h2>Contacts</h2>
      <ul>
        <li>
          <b>Email：</b>
          <a href="mailto:me@skyrocketing.ninja">me#skyrocketing.ninja</a>
        </li>
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
  width: 42px;
  height: 42px;
  border-radius: 50%;
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
</style>
