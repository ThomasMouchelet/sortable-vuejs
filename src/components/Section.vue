<template>
    <div class="section">
        <input type="text" v-model="section_title">

        <div class="container_lessons">
            <draggable 
                tag="ul" 
                :list="lessons" 
                group="lessons" 
                class="list-group" 
                handle=".handle"
                ghost-class="ghost"
            >
                <li
                class="list-group-item"
                v-for="(lesson, idx) in lessons"
                :key="lesson.id"
                >
                    <i class="fa fa-align-justify handle"></i>
                    <input type="text" v-model="lesson.lesson_title" />
                    <i class="fa fa-times close" @click="removeAt(idx)"></i>
                </li>
            </draggable>
            <form action="" v-on:submit.prevent="onSubmit">
                <input type="text" placeholder="Add Lesson" v-model="newLesson">
            </form>
        </div>
    </div>
</template>


<script>
import draggable from 'vuedraggable'

export default {
    name: "section",
    props: ['section_title', 'lessons'],
    newLesson:'',
    components: {
        draggable
    },
    methods: {
        onSubmit: function(){
            this.lessons.push({ lesson_title: this.newLesson });
            this.newLesson = ''
        },
        removeAt(idx) {
            this.lessons.splice(idx, 1);
        }
    }
}
</script>

<style>
.container_lessons{
    margin-left: 50px
}
li{
    list-style: none;
    display: flex;
    align-items: center;
    justify-content: space-around;
}
.handle, .close{
    cursor: pointer;
}
.ghost {
  opacity: 0.5;
  background: #c8ebfb;
}
</style>