<template>
    <section>
        <ul>
            <li v-for="(todoItem, index) in propsdata" class="shadow" v-bind:key="index">
                <i class = "checkBtn fas fa-check" aria-hidden="true"></i>
                {{todoItem}}
                <span class="removeBtn" type="button" @click="removeTodo(todoItem, index)">
                    <i class ="far fa-trash-alt" aria-hidden="true"></i>
                </span>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    props: ['propsdata'],
    methods:{
        removeTodo(todoItem, index){
            localStorage.removeItem(todoItem);
            this.todoItems.splice(index, 1);
        }
    }
}
</script>

<style scoped>
ul{
    list-style-type: none;
    padding-left: 0px;
    margin-top: 0;
    text-align: left;
}
li{
    line-height: 45px;
    display: flex;
    min-height: 50px;
    height: 50px;
    margin: 0.5rem 0;
    padding: 0 0.9rem;
    background: white;
    border-radius: 5px;
}
.checkBtn{
    line-height: 45px;
    color:#62acde;
    margin-right: 5px;
}
.removeBtn{
    line-height: 45px;
    margin-left: auto;
    color: #de4343;
}
</style>