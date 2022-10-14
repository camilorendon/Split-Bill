<script setup>
import {defineProps, ref} from 'vue';
import { pay} from "../store/store"

const props = defineProps(['id', 'numberOfPerson', 'totalPerperson', 'Paid']);
const paid = ref(false);

function handleChange(e){
    paid = e.target.value;

    pay(props.id, paid)
}


</script>

<template>
    <div>
        <div class="person-number">
            person {{props.numberOfPerson}}
        </div>
        <div class="person-to-pay">
                {{
                        new Intl.NumberFormat('en-Us', {
                            style: "currency",
                            currency: "USD",
                    }).format(props.totalPerPerson)
                }}
        </div>

        <div class="paid">
            <input type="checkbox" name="" id="" @change="handleChange"/> Paid
        </div>
    </div>

</template>

<style scoped></style>

