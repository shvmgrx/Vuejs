<template>
    <div class="test">
        <input type="text" v-model="title"><br>
        <h1>{{title}}</h1>
        <p>{{user.firstName}}</p>
        <p v-if="showName">{{user.firstName}}</p>
        <p v-else>Nobody</p>
        <ul>
        <li v-for="item in items">{{item.title}}</li>
        </ul>
        <button v-on:click="greet(title)">Click me bruh</button>

        <!-- Alternative way to display
        <p v-text="user.firstName"></p>
        --> 
    </div>
</template>

<script>
    export default {
        name: 'test',
        data(){
            return{
                title:'Coffee',
                user:{
                    firstName:'Shivam',
                    lastName:'Goraksha'
                },
                showName:false,
                items:[
                    {title:'Item One'},
                    {title:'Item Two'},
                    {title:'Item Three'}

                ]
            }
        },
        methods:{
            greet: function(title){
                alert('Moin Moin'+ " "+title);
            }
        }
    }
</script>

<style scoped>

</style>