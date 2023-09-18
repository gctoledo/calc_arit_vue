<script setup>
const props = defineProps(['getNumber', 'getOperator', 'result'])
</script>

<template>
    <div class="calc">
        <input type="number" @keyup="props.getNumber" id="num1" placeholder="Valor 1">
        <select @change="props.getOperator">
            <option selected value="+">+</option>
            <option value="-">-</option>
            <option value="/">/</option>
            <option value="*">*</option>
        </select>
        <input type="number" @keyup="props.getNumber" id="num2" placeholder="Valor 2">
        <span class="result">{{ props.result }}</span>
    </div>
</template>

<style scoped>
input,
select {
    padding: 12px;
    border-radius: 5px;
}

select {
    margin: 0 10px 0 10px;
}

.result {
    display: block;
    margin-top: 32px;
    font-size: 24px;
}
</style>