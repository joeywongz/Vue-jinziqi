<template>
    <div>
        <div class="cell" @click="onClickSelf">
            <template v-if="a">{{text}}</template>
            <template v-else></template>
        </div>
    </div>

</template>

<script>
    export default {
        props: ["n","winner"],
        data() {
            return {
                a: false,
                text: "",
            }
        },
        methods: {
            onClickSelf() {
                if(this.text!==""){
                    return
                };
                if(this.winner){
                    return
                };
                this.a = true;
                this.text = this.n % 2===0?"x":"o";
                this.$emit("click", this.text);
            }
        },
    }
</script>

<style>
    .cell {
        border: 1px solid black;
        height: 100px;
        width: 100px;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 80px;
    }
</style>