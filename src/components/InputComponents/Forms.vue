<template>
    <TextInput/>
    <EmailInput/>
    <PasswordInput/> 
    <button>Submit</button>   
</template>
<script>
import EmailInput from './FormInput/EmailInput.vue'
import PasswordInput from './FormInput/PasswordInput.vue'
import TextInput from './FormInput/TextInput.vue'

export default {
    components:{
        TextInput,
        EmailInput,
        PasswordInput
    }
}
</script>
<style scoped>

</style>