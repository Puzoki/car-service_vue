<script setup>
import { cars } from '../test_data/car.js';
</script>

<template>
    <div class="container">
        <div class="cars">
            <div v-for="car in cars" class="car">
                <!-- v-if="component !== 'qrcode'" style="background-color: #f8f9fa;"> -->
                <div class="car-malfunction">{{ car.malfunction }}</div>
                <div class="car-brand">{{ car.brand }}</div>
                <div class="car-model">&nbsp&nbsp&nbsp{{ car.model }}</div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.subm {
    position: absolute;
    right: 0;
    top: 0;

    background-color: rgba(0, 0, 0, 0);
}

.container {
    max-height: 92vh;
    position: absolute;
    top: 8vh;
    left: 0;
}

.cars {
    width: 100%;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.car {
    width: 100%;
    display: flex;
    flex-flow: row wrap;
    box-sizing: border-box;
    padding: 1rem;
    text-align: left;
}

.car:active {
    background-color: #dedede;
}

.car-malfunction {
    width: 100%;
    font-size: 1.2rem;
    color: #212121;
}

.car-brand {
    /* width: 40%; */
    color: gray;
    font-size: 1.1rem;
    margin-left: .4rem;
}

.car-model {
    /* width: 60%; */
    color: gray;
    font-size: 1.1rem;
}
</style>
