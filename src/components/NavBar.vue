<template>
    <div class="nav-bar">
        <div class="nav-item">
            <b>To Do App</b>
        </div>
        <div class="nav-item">
            <a href="http://www.github.com/shwetasharma21" ><img src="../assets/github.svg" alt=""/></a>
        </div>
    </div>
</template>

<script>
export default{
    name:"NavBar"
}
</script>

<style scoped>
    .nav-bar{
        display: flex;
        flex-direction: row;
        background-color: black;
        justify-content: space-between;
        
    }
    .nav-item{
        padding: 1rem;
        color: white;
        justify-content: center;
        display: flex;
        align-items: center;
    }
</style>
