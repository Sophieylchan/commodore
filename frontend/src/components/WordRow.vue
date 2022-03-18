<template>
    <div>
        <div class="word_row">
            <p v-for="(letter, index) in splitWord" :key="letter + index" class="single_letter">{{ letter }}</p>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        'word'
    ],
    computed: {
        splitWord() {
            let arr = [];
            for (let i = 0; i < 5; i++) {
                if (this.word[i]) {
                    arr.push(this.word[i])
                } else {
                    arr.push('')
                }
            }
            return arr
        },
    },
}
</script>

<style>
    .word_row {
        display: grid;
        grid-template-columns: repeat(5, 5rem);
        grid-template-rows: 5rem;
        gap: 1rem;
        justify-content: center;
        align-items: center;
        height: 5rem;
        margin-bottom: 1rem;
    }

    .single_letter {
        border: solid 2px #707070;
        border-radius: 5px;
        height: 5rem;
        margin-bottom: 0;
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 1.5rem;
    }
</style>