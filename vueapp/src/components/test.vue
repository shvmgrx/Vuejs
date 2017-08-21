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
        <br>
        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
        <br>
        <label>First name:</label>
        <input type="text" v-model="user.firstName">
        <br>
        <label>Last name:</label>
        <input type="text" v-model="user.lastName">
        <br>
        <h3>{{fullName}}</h3>
        <br>
        {{msg}}


        <!-- Alternative way to display
        <p v-text="user.firstName"></p>
        --> 
    </div>
</template>

<script>
    export default {
        name: 'test',
        props:{
            msg:{
                type:String,
                default:'Foobar'
            }
        },
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
            },
            pressKey: function(e){
                console.log(e.target.value);
            },
            enterHit: function(){
                console.log('You hit enter');
            }
        },
        computed:{
            fullName: function(){
                return this.user.firstName+' '+this.user.lastName;
            }
        }
    }
</script>

<style scoped>

</style>