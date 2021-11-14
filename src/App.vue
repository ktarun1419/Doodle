<template>
  <div id="app">
    <div class="navbar">
        <img src="./views/opensea.svg" width="50px" height="30px" style="float:left; margin-left:5%; margin-top:1%;">
        <h2 style="color:black; float:left; margin-left:1%;margin-top:2%;">OpenSea</h2>
        <input style="border-radius:10px;margin-top:1%; float:left; width:30%; margin-left:5%;padding: 8px 10px;" placeholder="Search items,collections and accounts">
        <a href="#/assets/0x8a90cab2b38dba80c64b7734e58ee1db38b8992e/8375" style="margin-top:1%;float:left;color:black; font-size:20px; margin-left:1%;">Explore</a>
  <a  href="#/assets/0x8a90cab2b38dba80c64b7734e58ee1db38b8992e/8375" style="margin-top:1%;float:left; color:black;font-size:20px;margin-left:1%;">Stats</a>
  <a href="#/assets/0x8a90cab2b38dba80c64b7734e58ee1db38b8992e/8375" style="margin-top:1%;float:left;color:black;font-size:20px;margin-left:1%;">Resources</a>
  <a href="#/assets/0x8a90cab2b38dba80c64b7734e58ee1db38b8992e/8375" style="margin-top:1%;float:left;color:black;font-size:20px;margin-left:1%;">Create</a>
        <md-icon style="margin-top:5px;float:right; margin-right:3% " class="md-size-2x"><span class="material-icons-outlined">
account_balance_wallet
</span></md-icon>
          <md-icon style="margin-top:5px;float:right; margin-right:3% " class="md-size-2x">
account_circle</md-icon>

</div>
    <router-view/>
    <link rel="stylesheet" href="//fonts.googleapis.com/css?family=Roboto:400,500,700,400italic|Material+Icons">
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: rgb(255, 255, 255);

}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}.navbar {
  overflow: hidden;
  background-color:white;
  position: fixed; /* Set the navbar to fixed position */
  top: 0; /* Position the navbar at the top of the page */
  width: 100%; /* Full width */
  margin-bottom: 30px;
  box-shadow: 1px 2px #888888;
  height: 10%;
}
/* Links inside the navbar */
.navbar a {
  display: inline-block;
  display: block;
  color: black;
  padding: 14px 16px;
  text-decoration: none;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 15px;
}
/* Change background on mouse-over */
.navbar a:hover {
  background-color: rgb(32, 129, 226);
  color:black;
  text-decoration: underline rgb(32, 129, 226);
}
</style>
