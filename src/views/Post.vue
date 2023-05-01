<template>
    <v-conatiner>
        <v-row>
            <v-col sm="10" class="pa-4 mx-auto">
                <v-card class="pa-2">
                    <v-img height="500" :src="`/${post.image}`"></v-img>
                    <v-card-action class="pb-0">
                        <v-row class="mt-1 mx-1">
                            <v-col sm="2">
                                <v-btn small outlined color="primary"> {{ post.category }}</v-btn>
                            </v-col>
                            <v-col sm="10" class="d-flex justify-end">
                                <v-btn text :to="{ name: 'edit-post', params: {
                                    id: post._id
                                }}">Edit</v-btn>
                                <v-btn color="red" text @click="deleteForm(post._id)">Delete</v-btn>
                            </v-col>
                        </v-row>
                    </v-card-action>
                    <v-card-subtitle class="headline">
                        <h3>{{ post.title }}</h3>
                    </v-card-subtitle>
                    <v-card-text class="grey--text">
                        <p>{{ post.content }}</p>
                        <p>{{ post.created }}</p>
                    </v-card-text>
                </v-card>
            </v-col>
        </v-row>
    </v-conatiner>
</template>

<script>
import API from '../api';

export default{
    data(){
        return{
            post: {},
        };
    },
    async created(){
        const response = await API.getPostByID(this.$route.params.id);
        this.post = response;
    },
    methods: {
        async deleteForm(id){
                const response = await API.deletePost(id);
                this.$router.push({ name: "HOME", params: { message: response.message}});
        }
    },
}
</script>
