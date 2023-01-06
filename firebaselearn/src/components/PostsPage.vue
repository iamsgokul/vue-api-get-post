<!-- <template>
    <div>PostPage</div>
</template> -->

 <template>
    <div>
        <div class="post" v-for="bpost in postsData" :key="bpost.id">
            <div class="ptitle">
                <h1>{{ bpost.title }}</h1>
                <p>{{ bpost.description }}</p>
            </div>
            <!-- <div class="pdescr">
                <p>{{ bpost.description }}</p>
            </div> -->
        </div>
    </div>
</template>


<script>
import axios from 'axios';


export default {
    data() {
        return {
            postsData: ''
        }
    },
    mounted() {
        this.getPosts();
    },
    methods: {
        getPosts() {
            axios.get(`https://vuebasic-b547c-default-rtdb.firebaseio.com/posts.json`).then(response => {
                console.log(response.data);

                this.postsData = response.data
            })
        }
    }
}
</script>



<!-- <template>
    <div>
        <div class="post" v-for="bpost in post" :key="bpost.id">
            <div class="ptitle">
                <h1>{{ bpost.title }}</h1>
            </div>
            <div class="pdescr">
                <p>{{ bpost.description }}</p>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';

export default {
    data() {
        return {
            post: {
                title: '',
                description: '',
            }
        }
    },
    mounted() {
        axios.get(`https://vuebasic-b547c-default-rtdb.firebaseio.com/posts`).then(response => {
            this.post = response.data
        })
    }
}
</script> -->