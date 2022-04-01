<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/databinding">Data Binding</router-link> |
    <router-link to="/boardlist">게시판</router-link> |
    <router-link to="/boardview">게시판뷰</router-link>
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#mainWrapper{
  width: 1080px;
  margin: 0 auto;
}

#mainWrapper > ul > li:first-child {
  text-align: center;
  font-size:14pt;
  height:40px;
  vertical-align:middle;
  line-height:30px;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
table.board_table {
  table-layout: auto;
  width: 100%;
  border-collapse: collapse;
  text-align: center;
  line-height: 1.5;
}
table.board_table thead th {
  padding: 10px;
  font-weight: bold;
  vertical-align: top;
  color: #369;
  border-bottom: 3px solid #036;
}
table.board_table tbody th {
  width: 150px;
  padding: 10px;
  font-weight: bold;
  vertical-align: top;
  border-bottom: 1px solid #ccc;
  background: #f3f6f7;
}
table.board_table td {
  width: 350px;
  padding: 10px;
  vertical-align: top;
  border-bottom: 1px solid #ccc;
}
</style>
