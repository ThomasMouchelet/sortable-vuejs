<template>
    <div class="lesson">
        <form v-on:submit.prevent="onSubmit">
            <input type="text" v-model="lesson_title">
        </form>
    </div>
</template>


<script>
export default {
    name: "lesson",
    props: ['lesson_title']
}
</script>

<style>
input{
    margin-left: 40px;
}
.fa-grip-vertical{
  cursor: pointer
}
</style>