<template>
    <input type="text" v-model="userModel.name.$model"/>
    
</template>

<script>
import { reactive } from 'vue'
import { useVuelidate } from "@vuelidate/core";
import { required } from "@vuelidate/validators";

export default {
    name: 'User',

    async setup() {

        const response = await fetch('https://jsonplaceholder.typicode.com/users/1');
        const user = reactive(await response.json());

        const validationRules = {
            name: { required }            
        };

        const userModel = useVuelidate(validationRules, user);

        return {
            userModel
        }

    }
}
</script>