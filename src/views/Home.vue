<template>
  <div class="home">
    <div class="hero">
      <h1 class="heading">Tangle Bay Dock</h1>
      <p class="sub-heading"><i18n path="nodedock"></i18n></p>
    </div>
    <div class="section">
      <div class="container">
        <NodeList />
      </div>
    </div>
    <div class="section section-background">
      <div class="container">
        <h2><i18n path="join"></i18n></h2>
        <p><i18n path="register"></i18n></p>
        <router-link to="/manage" class="nav-item" exact-active-class="active">
          <i18n path="register2"></i18n>
        </router-link>
        <br>
      </div>
    </div>
  </div>
</template>

<script>
import NodeList from "../components/NodeList";

export default {
  name: "Home",
  components: { NodeList },
  data() {
    return {
      copied: false,
      url: "https://nodes.tanglebay.org"
    };
  },
  methods: {
    onCopy() {
      this.copied = true;
      console.log("copy success!");
      setTimeout(
        function() {
          console.log("what?");
          this.copied = false;
        }.bind(this),
        1000
      );
    },
    onError() {
      console.log("copy error!");
    }
  }
};
</script>

<style lang="scss">
.el-main {
  padding: 0px !important;
}
.home {
  text-align: center;
}
.hero {
  margin: 0 10px;
}
.section {
  padding: 80px 0;
  &-background {
    color: var(--white);
    background-color: var(--dark);
    p {
      max-width: 600px;
      margin: 15px auto 30px;
    }
    a {
      text-decoration: none;
    }
  }

  .headline-wrapper {
    padding: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
@media only screen and (max-width: 740px) {
  .hero {
    padding-top: 40px;
  }
  .headline-wrapper {
    flex-wrap: wrap;
    h2 {
      margin-bottom: 20px;
    }
  }
  .btn-social {
    margin-bottom: 5px !important;
  }
}
</style>