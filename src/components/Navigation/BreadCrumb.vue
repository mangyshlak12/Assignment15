<template>
    <ul class="breadcrumb">
        <li><a href="">Hello</a></li>
        <li><a href="">World</a>
        </li>
        <li><a href="">Student</a></li>
        <li>SDU</li>
    </ul>
</template>
<script>
export default {
    
}
</script>
<style scoped>
.breadcrumb{
    padding: 10px 16px;
    list-style: none;
    background-color: #eee;
}
ul li{
    display: inline;
    font-size: 18px;
}
ul li+li::before{
    padding: 8px;
    color: black;
    content: "/\00a0";
}
ul li a{
    text-decoration: none;
    color: black;
}
</style>