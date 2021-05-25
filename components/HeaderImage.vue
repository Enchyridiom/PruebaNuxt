<template>
    <div>
        <img :src="source" alt="demo">
        <h2>{{saludo}}</h2>
        <h3>{{demo}}</h3>
        <h1>{{end}}</h1>
    </div>
</template>

<script>
export default{
    props: ["source", "saludo", "end", "demo"]
}
</script>

<style>
</style>