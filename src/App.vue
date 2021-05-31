<template>
  <div id="app">
    <div class="container">
      <Header/>
      <div class="page">
        <SideBar/>
        <Users/>
      </div>

    </div>


  </div>
</template>

<script>


  import SideBar from "./components/SideBar";
  import Header from "./components/Header";
  import Users from "./components/Users";

export default {
  name: 'App',
  components: {
    Users,
    Header,
    SideBar

  }
}
</script>

<style lang="scss">
  #app {
    font-family: 'Montserrat', sans-serif;
    background-color: #F0F6FC;

    .container {
      height: 100%;
      padding: 10px 38px 0;
    }

    .page {
      display: flex;

    }
  }

  button {
    background-color: white;
    border: none;
  }

  body {
    margin: 0;
  }

  .bg-w {
    background-color: white;
  }

  .bg-g {
    background: rgba(203, 215, 228, 0.4);
  }
</style>
