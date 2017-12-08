<template>
    <main class="faq">
        <h1>Frequently Asked Questions</h1>

        <div class="error" v-if="hasRemoteErrors">
            Can't load the questions
        </div>

        <section class="list">
            <article v-for="question of questionList">
                <h2 v-html="question.title"></h2>
                <p v-html="question.content"></p>
            </article>
        </section>
        <Loading v-if="remoteDataLoading" />
    </main>
</template>

<script>
    import RemoteData from '../mixins/RemoteData'

    export default {
        mixins: [
            RemoteData({
                questionList: 'questions'
            }),
        ],
        // data() {
        //     return {
        //         error: null,
        //         loading: false,
        //     }
        // },
        // created() {
        //     fetch('http://localhost:3000/questions').then(response => {
        //         if (response.ok) {
        //             return response.json()
        //         } else {
        //             return Promise.reject('error')
        //         }

        //     }).then(result => {
        //         // Result is the JSON parsed object from the server
        //         this.questions = result
        //     }).catch(e => {
        //         this.error = e
        //     })
        // }
        // async created() {
        //     this.loading = true
        //     try {
        //         this.questions = await this.$fetch('questions')
        //         // if (response.ok) {
        //         //     this.questions = await response.json()
        //         // } else {
        //         //     throw new Error('error')
        //         // }
        //     } catch (e) {
        //         this.error = e
        //     }
        //     this.loading = false
        // },
    }
</script>