<template>
    <div>
        <h2>{{ title }}</h2>
        <h3 @click="changeTitle">{{subtitle}}</h3>
        <p :id="firstId">{{ content }}</p>
        <p v-html="content" :id="secondId"></p>
        <select name="" id="">
            <option v-for="author in authors" :key="author" value="">
                {{author}}
            </option>
        </select>
        <button @click="removeLastAuth">Remove last</button>
    </div>
</template>

<script>
    export default {
        name : "ChildComp",

        
        props: {
            title: {
                type: String,
                default: "I'm a ChildComp"
            },
        },


        data() {
            return {
                content : "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Labore vitae tenetur nostrum fugiat voluptas laboriosam, quam aperiam nulla quasi maiores error nisi odit necessitatibus.",
                firstId : "contentPara",
                secondId : "italic",
                subtitle : "This is a subtitle",
                isSubtitleActive : false,
                authors : [ "King", 
                            "Orwell", 
                            "Stein", 
                            "Grisham", 
                            "Shakespere", 
                            "Goethe", 
                            "Erikson", 
                            "Bradbury", 
                            "Seuss", 
                            "Gogol" ]
            }
        },


        methods: {
            changeTitle() {
                this.isSubtitleActive = !this.isSubtitleActive;
                if (this.isSubtitleActive){
                    this.subtitle = "You clicked me!"
                } else {
                    this.subtitle = "This is a subtitle";
                }
            },
            removeLastAuth(){
                this.authors.reverse();
            }
        },
    }
</script>

<style scoped>
div {
    background-color: rgb(18, 184, 148);
}

#italic{
    font-style: italic;
    font-size: 1.3em;
}

* {
    background-color: inherit;
}

h3 {
    user-select: none;
}

</style>