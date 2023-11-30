<script setup>
    import { ref } from 'vue'

    const text = ref('Edit me')
    const checked = ref(true)
    const checkedNames = ref(['Jack'])
    const picked = ref('하나')
    const selected = ref('A')
    const multiSelected = ref(['A'])
    
</script>

<template>
    <h2>Text Input</h2>
    <input v-on:keyup="text=$event.target.value"> {{ text }}

    <h2>Checkbox</h2>
    <input type="checkbox" id="cb" v-model="checked">
    <label for="checkbox">
        Checked: {{ checked }}
    </label>

    <h2>Multi Checkbox</h2>
    <input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
    <label for="jack">Jack</label>
    <input type="checkbox" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label>
    <p>Checked names: <pre>{{ checkedNames }}</pre></p>

    <h2>Radio</h2>
    <input type="radio" id="one" value="하나" v-model="picked">
    <label for="one">하나</label>
    <br>
    <input type="radio" id="two" value="둘" v-model="picked">
    <label for="two">둘</label>
    <br>
    <span>Picked: {{ picked }}</span>

    <h2>Select</h2>
    <select v-model="selected">
        <option disabled value="">Please select one</option>
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
    <span>Selected: {{ selected }}</span>

    <h2>Multi Select</h2>
    <select v-model="multiSelected" multiple style="width:100px">
        <option>A</option>
        <option>B</option>
        <option>C</option>
    </select>
    <span>Selected: {{ multiSelected }}</span>

</template>