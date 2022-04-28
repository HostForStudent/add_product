<template>
<div class="c-title">
   {{text}}
</div>
</template>

<script>
export default {
   props:['text']
};
</script>

<style lang="less">
.c-title{
background: rgba(22, 114, 213, 0.03);
border: 1px solid rgba(22, 114, 213, 0.25);
box-sizing: border-box;
padding: 20px 27px;
font-style: normal;
font-weight: 500;
font-size: 18px;
line-height: 21px;
color: #021121;
}
</style>