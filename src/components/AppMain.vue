<template lang="">
    <section>
        <div class="container">
            <div class="row">
                <div class="col-12">
                    <h2>
                        Posts:
                    </h2>                 
                </div>
                <div class="col-6 single-post" v-for="post in posts">
                    {{post.title}}
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import axios from 'axios';

export default {
    name: 'AppMain',
    data() {
        return {
            posts: [],
            loading: false,
            urlAddress: 'http://127.0.0.1:8000/api/post',
        }
    },

    methods: {
        getPosts() {
            axios.get(this.urlAddress, {
                params: {
                }
            })
                .then((response) => {
                    this.posts = response.data.results;
                    console.log(this.posts)
                })
                .catch(function (error) {
                    console.log(error);
                });
        }
    },


    created() {
        this.getPosts();
    },

}
</script>

<style scoped lang="scss"></style>