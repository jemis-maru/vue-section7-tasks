<template>
    <ul>
        <li>
            <h2>{{ fr.name }}</h2>
            <button @click="toggleDetails">{{ btnTextFun }}</button>
            <ul v-show="detailsToggle">
                <li><strong>Phone: </strong>{{ fr.phNo }}</li>
                <li><strong>Email: </strong>{{ fr.emailAdd }}</li>
            </ul>
        </li>
    </ul>
</template>

<script>
export default {
    name: 'FriendData',
    props:{
        fr: {
            type: Object,
        },
    },
    data(){
        return{
            detailsToggle: false,
        }
    },
    methods:{
        toggleDetails(){
            this.detailsToggle = !this.detailsToggle;
        },
    },
    computed:{
        btnTextFun(){
            if(this.detailsToggle){
                return 'Hide details';
            }
            else{
                return 'Show details';
            }
        },
    },
}
</script>