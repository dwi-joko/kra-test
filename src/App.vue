<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/blog">Blog</router-link>
  </div>
  <router-view />
</template>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  position: relative;

  #nav {
    padding: 30px;
    position: absolute;
    z-index: 9;
    width: 100%;
    color: #fff;
    box-sizing: border-box;

    a {
      font-weight: bold;
      color: #ffffff;

      &.router-link-exact-active {
        color: #42b983;
      }
    }
  }
  .page-wrapper {
    .banner {
      height: 600px;
      position: relative;
      &:after {
        content: "";
        background: #000000b8;
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
      }
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
    .articles {
      padding: 60px 0;
      ul {
        display: inline-block;
        padding: 0;
        margin: 0;
        width: 100%;
        max-width: 1200px;
        li {
          list-style-type: none;
          width: 33.333%;
          display: inline-block;
          padding: 15px;
          box-sizing: border-box;
          text-align: left;
          a {
            cursor: pointer;
            .image {
              img {
                width: 100%;
                object-fit: cover;
              }
            }
            h3 {
              margin: 0;
              padding: 10px 0;
            }
            p {
              display: -webkit-box;
              -webkit-line-clamp: 4;
              -webkit-box-orient: vertical;
              overflow: hidden;
              margin: 0;
            }
          }
        }
      }
    }
  }
}

// responsive
@media screen and (max-width: 480px) {
  #app {
    .page-wrapper {
      .banner {
        height: 300px;
        position: relative;
      }

      .articles {
        ul {
          li {
            width: 100%;
          }
        }
      }
    }
  }
}
</style>
