<template>
    <div class="wrapper">
        <div class="anchor-tags">
        <a href="#">Home</a>
        <a href="#">Products</a>
         <a href="#">Contact</a>
        <a href="#">More</a>
        </div>
        <input type="text" placeholder="Search">
        <p class="cart">🛒</p>
        
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>
.wrapper{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 0px;
    background-color: #5bccf6;
}
.anchor-tags a{
    margin: 25px;
    font-weight: bold;
    color: #030e12;
    text-decoration: none;
}

.wrapper input{
    padding: 2px 4px;
    margin-right: 340px;
    border:none;
    border-radius: 5px;
}
.wrapper p{
    width: 30px;
    height: 30px;
    border: solid 1px #000;
    border-radius: 100%;
    margin-right: 30px;
    font-size:1.2rem;

    display: flex;
    justify-content: center;
    align-items: center;
}
</style>