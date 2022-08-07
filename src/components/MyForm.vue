<template>
    <div>
        <p>{{ name }}</p>
        <input ref="el" type="text" placeholder="Name" v-model="name" />
        <div>
            <button @click = "submitForm"
                v-bind:disabled="name.length === 0"
            >Submit</button>
        </div>
    </div>
</template>

<script>
import {ref, onMounted} from 'vue'

export default {
    setup () {
        const name = ref('');
        const el = ref('');

        const submitForm = () => {
            console.log(name._value)
            alert(name._value + ', 입력되었습니다!');
        }

        onMounted(()=>{
            el.value.focus();
        })

        return {
            el,
            name,
            submitForm
        }
    }
}
</script>

<style lang="scss" scoped>

</style>