<template>
    <div>
        <WordRow v-for="(word, index) in words" :key="word + index" :word="word" :active="activeWord === index"/>
    </div>
</template>

<script>
import WordRow from './WordRow.vue'
export default {
    components: {
        WordRow
    },
    props: [
        'words'
    ],
    data() {
        return {}
    },
}
</script>