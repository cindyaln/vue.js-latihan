<template>
    <div>
        <!--<h1> hallo dunia </h1>-->
        <!-- <p> ini komponen gue </p>-->

        <p> nama kamu : {{ nama }}</p>
        <p> umur kamu : {{ umur }}</p>

    </div>
</template>

<script>
export default {
    nama : "MyComponent", 
    props : ['nama', 'umur'],
    data () { 
        return {
            message : "ini pesan dari component"
        }
    },
    methods : {
        greet () {
            console.log ("hallo");
        }
    },
}
</script>

<style>
h1 {
    color : blue;
} 
p {
    font-size : 16px;
}
</style>