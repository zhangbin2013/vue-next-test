<template>
    <div class="test">
        <h1>vue3.0 初体验</h1>
        <p>少年你的头发可还好，？？？？ 哈哈哈哈哈</p>
        <h1>test count: {{count}}</h1>
        <div>count * 2 = {{doubleCount}}</div>
        <input type="text" v-model="count">
        <div>state from vuex {{a}}</div>
        <button @click="add">add</button><br/>
        <button @click="update">update a</button>
    </div>
</template>

<script>
    import { ref, computed, watch, getCurrentInstance } from 'vue';

    export default {
        setup() {
            const count = ref(0);
            const add = () => {
                count.value++;
            };
            watch(() => count.value, val => {
                console.log(`count is ${val}`);
            });
            const doubleCount = computed(() => count.value * 2);

            const { ctx } = getCurrentInstance()
            console.log(ctx.$router.currentRoute.value)
            const a = computed(() => ctx.$store.state.test.a)
            const update = () => {
                ctx.$store.commit('setTestA', count)
            }
            return {
                count,
                add,
                doubleCount,
                a,
                update
            };
        }
    };
</script>

<style lang="scss" scoped>
    .test {
        color: grey;
    }
</style>