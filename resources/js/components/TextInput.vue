<template>
    <div>
        <div class="title-text">{{ title }}</div>
        <component
            :is="isArea ? 'TextArea' : 'input'"
            type="text" 
            :name="name" 
            class="text-input" 
            :placeholder="hint"
            :maxlength="max"
            v-bind:value="value"
            v-on:input="$emit('input', $event.target.value)"
            :style="{
                minHeight: minHeight
            }">{{ isArea ? value : ''}}</component>
    </div>
</template>

<script>
export default {
    props: [
        'value',
        'title', 
        'name', 
        'hint', 
        'max', 
        'minHeight', 
        'isArea'
    ],
}
</script>

<style scoped>
.text-input {
    border: 1px solid lightgray;
    border-radius: 1px;
    width: 100%;
    padding: 1em 1em;
    font-size: 16px;
}

.text-input::placeholder {
    color: lightgray;
}

</style>
