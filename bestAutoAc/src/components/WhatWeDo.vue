<template>
    <div class="flex-container">
        <div class="info1">
        <h1>Our services</h1>
        <ul>
            <li>AC top off</li>
            <li>AC extraction (if you need your system emptied then returned)</li>
            <li>Diagnosing of ac system</li>
            <li>AC system repairs</li>
        </ul>
    </div>
    <div class="info2">
        <h1>Our Rates</h1>
        <ul>
            <li>AC refrigerant @4.99 per ounce</li>
            <li>Service fee $29.99</li>
            <li>$80 per hour labor if system repairs are needed</li>
        </ul>
        <h1>We only charge you for what you need!</h1>
    </div>
    </div>

</template>
<style scoped>
    .flex-container{
        display: flex;
        flex-direction: row;
    }

    .info1{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border: 3px solid gray;
        width: 50%;
        height: 50vh;
    }
    .info2{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        border: 3px solid grey;
        width: 50%;
        height: 50vh;
    }

</style>