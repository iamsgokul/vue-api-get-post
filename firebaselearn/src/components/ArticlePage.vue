<template>
    <div>Posts Data</div>
    <div v-if="!posts">Loading Post Data</div>
    <table>
        <thead>
            <tr>
                <th>Id</th>
                <th>Title</th>
                <th>Body</th>
            </tr>
        </thead>
        <tbody>
            <tr v-for="post in posts" :key="post.id">
                <td>{{ post.id }}</td>
                <td>{{ post.title }}</td>
                <td>{{ post.body }}</td>
            </tr>
        </tbody>
    </table>
</template>

<script>

import axios from 'axios';
export default {
    data() {
        return {
            posts: '',
        }
    },
    mounted() {
        axios.get(`https://jsonplaceholder.typicode.com/posts`).then(response => {
            // console.log(response.data);
            this.posts = response.data;
        });
    }
};
</script>

<style scoped>
table{
    border:1px solid #dddddd;
    border-collapse: collapse;
}
table tr{

}

table tr td{

    text-align: left;
    border-bottom:1px solid #dddddd;
}
</style>