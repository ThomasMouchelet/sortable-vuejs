<template>
    <div class="course">
        <h1>Course</h1>
        <div v-for="section in sections" :key="section.id" class="sections">
            <Section 
                v-bind:section_title="section.section_title"
                v-bind:lessons="section.lessons"
            />
        </div>
        
        <form action="" v-on:submit.prevent="onSubmit">
            <input type="text" placeholder="Add Section" v-model="newSection">
        </form>
    </div>

</template>   


<script>
import Section from './Section'

export default {
    name: "course",
    newSection:'',
    components: {
        Section
    },
    data() {
        return {
            sections: [
                {
                    section_title:"Section 1", 
                    id:0,
                    lessons:[
                        {lesson_title:"lesson 1-1", id:0},
                        {lesson_title:"lesson 1-2", id:0}
                    ]
                },
                {
                    section_title:"Section 2",
                    id:1,
                    lessons:[
                        {lesson_title:"lesson 2-1", id:0}
                    ]
                }
            ]
        }
    },
    methods: {
        onSubmit: function(){
            this.sections.push({ section_title: this.newSection });
            this.newSection = ''
        },
        clone: function(el) {
            return {
                name: el.name + " cloned"
            };
        }
    }
}
</script>

<style>
.crouse{
    width: 600px;
}
</style>