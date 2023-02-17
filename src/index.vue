<script>
    // import { defineComponent } from 'vue';
    import axios from 'axios';
    import flow from './components/flow.vue';
    
    export default {
        async mounted() {
            let res = await this.getCatFact();
            this.fact = res.fact;
        },

        methods: {
            async getCatFact() {
                let res = await axios.get("https://catfact.ninja/fact");
                return res.data;
            }
        },

        data() {
            return {
                fact: null
            }
        }
    }
</script>

<template>
    <h1>Hello, world!</h1>
    <p> Cat fact: {{ fact }} </p>
    <hr/>
    <flow />
</template>
