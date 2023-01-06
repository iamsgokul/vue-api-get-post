<template>
    <div>
        <form @submit.prevent="onAddPost">
            <div class="fld-grp">
                <label>Title</label>
                <input type="text" v-model="post.title" />
            </div>
            <div class="fld-grp">
                <label>Comment</label>
                <textarea v-model="post.description"></textarea>
            </div>
            <div class="fld-grp">
                <button>Add Post</button>
            </div>
        </form>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            post: {
                title: '',
                description: ''
            }
        };
    },
    methods: {
        onAddPost() {
            // console.log(this.posts);

            axios.post(`https://vuebasic-b547c-default-rtdb.firebaseio.com/posts.json`, this.post).then(response => {
                console.log(response);
            })
        }
    },
};
</script>

<style scope>
.fld-grp {
    width: 50%;
    margin: 10px auto 10px;
}

.fld-grp label {
    font-size: 16px;
    font-weight: bold;
    display: block;
    width: 50%;
    text-align: left;
    margin-bottom: 10px;
}

.fld-grp input[type="text"] {
    font-size: 14px;
    font-weight: bold;
    display: block;
    width: 100%;
    margin: auto;
}

.fld-grp textarea {
    font-size: 14px;
    font-weight: bold;
    width: 100%;
}

.fld-grp button {
    padding: 8px 10px;
    text-align: left;
    border: 0;
    background-color: brown;
    display: flex;
    color: #ffffff;
}
</style>