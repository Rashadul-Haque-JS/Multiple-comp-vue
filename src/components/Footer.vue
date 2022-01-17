<template>
    <div class="symbol">
        <div>
            <p>🔴</p>
            <p>🟠</p>
            <p>🟡</p>
            <p>🟢</p>
        </div>
        <div>
            <p>🍔</p>
            <p>🍟</p>
            <p>🥗</p>
            <p>🥤</p>
        </div>
         <div>
            <p>📕</p>
            <p>📗</p>
            <p>📘</p>
            <p>📃</p>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style  scoped>
.symbol{
  display: flex;
  justify-content: space-between;
  align-items: center;
    background-color: #030e12;
    padding: 20px 0px;
    color: #fff;
    text-align: center;
}

.symbol div{
    display: flex;
}
.symbol p{
    
    width: fit-content;
    margin: 10px;
}
</style>