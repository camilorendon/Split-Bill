<script setup>
import { ref } from 'vue';
import {store, calculate} from "../store/store"
const total =ref(0);
const tip =ref(0);
const people =ref(0);

function handleSubmit(){
    store.params.total =total;
    store.params.tip = tip;
    store.params.people= people;
    calculate();
}

</script>

<template>
   <form action="" @submit.prevent="handleSubmit">
    <div class="form-container">
        <div>
            <lavel for="total">Total</lavel>
            <input type="numer" required v-model="total" />
        </div>

        <div>
            <lavel for="tip">tip %</lavel>
            <input type="numer" required v-model="tip" />
        </div>

        <div>
            <lavel for="people">people</lavel>
            <input type="numer" required v-model="people" />
        </div>
        <div>
            <input type="submit" value="calculate"/>
        </div>

    </div>
   </form>
</template>

<style scoped></style>