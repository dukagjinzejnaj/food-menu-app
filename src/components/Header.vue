<script>
export default {
  props: {
    switchMode: String
  }
}
</script>

<template>
    <div class="header">
        <h1>Food Menu App</h1>
        <button @click="$emit('btn-click-darkMode')">{{ switchMode }}</button>
    </div>
</template>