<template>
    <div class="convertedData-wrapper">
        <pre class="convertedData">{{ text }}</pre>
    </div>
</template>

<script>
export default {
    name: 'convertedData',
    props: {
      text: String,
    }
}
</script>

<style scoped>
.convertedData-wrapper {
    width: 45vw;
    border: 1px dashed #444;
    overflow: hidden;
}

.convertedData {
    width: 45vw;
    padding: 20px;
    margin: 0 !important;
    text-align: left;
    overflow: auto;
}
</style>
