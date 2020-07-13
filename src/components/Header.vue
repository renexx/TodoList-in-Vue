<template>
    <header class="header">
     
        <h1>Todo app</h1>
    </header>
</template>


<script>
export default {
    name:"Header"
}
</script>

<style scoped>
.header {
    background-color: rgb(61, 60, 60);
    color: #fff;
    text-align: center;
    padding: 10px;
    height: 150px;
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    text-transform: uppercase;
  }
  .header a {
    color: #fff;
    padding-right: 5px;
    text-decoration: none;
  }
 
</style>