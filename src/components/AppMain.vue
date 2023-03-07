<template lang="">
    <section>
        <div class="container">
            <div class="row g-5">
                <div class="col-12">
                    <h2>
                        Posts:
                    </h2>                 
                </div>
                <div class="row justify-content-around">
                    <div class="col-6 single-post card mb-3  p-3" v-for="post in posts">
                        <img src="{{post.cover_image}}" class="card-img-top" alt="...">
                        <div class="card-body">
                            <h5 class="card-title">{{post.title}}</h5>
                            <p class="card-text">{{post.content.substr(0,300)}}...</p>
                            <a href="#" class="btn btn-primary">Show</a>
                        </div>  
                    </div>
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