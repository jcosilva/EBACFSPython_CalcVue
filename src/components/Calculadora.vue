<script setup>
    const props = defineProps(['valor1', 'valor2', 'trocarOperador', 'editaValor1', 'editaValor2', 'resultado']);
</script>

<template>
    <form>
        <div class="row">
            <div class="col-md-3 mb-3">
                <b>Valor #01:</b>
                <input type="number" class="form-control" placeholder="Digite Valor #1" :value="props.valor1" @change="props.editaValor1" required>
            </div>
            <div class="col-md-3 mb-3">
                <b>Operador:</b>
                <select @change="props.trocarOperador" class="form-control">
                    <option value="mais">+ (mais)</option>
                    <option value="menos">- (menos)</option>
                    <option value="vezes">x (vezes)</option>
                    <option value="dividir">/ (dividir)</option>
                </select>
            </div>
            <div class="col-md-3 mb-3">
                <b>Valor #2:</b>
                <input type="number" class="form-control" placeholder="Digite Valor #2" :value="props.valor2" @change="props.editaValor2" required>
            </div>
            <div class="col-md-3 mb-3">
                <b>Resultado:</b>
                <label class="form-control">{{ resultado.toFixed(5) }}</label>
            </div>
        </div>
    </form>
</template>