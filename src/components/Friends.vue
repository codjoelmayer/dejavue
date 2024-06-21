<template>
    <div class="container">
        <div class="row">
            <h2 class="display-2">Best Friends</h2>
        </div>
        <div class="row gap-2 justify-content-center" v-if="friends.length">
            <Card v-for="friend in friends" :key="friend.id" :class="{
            male: friend.gender.toLowerCase() == 'male',
            female: friend.gender.toLowerCase() == 'female'
        }">
                <template #cardHeader>
                    <img :src="friend.profile" :alt="friend.firstName" class="img-fluid" loading="lazy">
                </template>
                <template #cardBody>
                    <p class="lead">{{ friend.firstName }} {{ friend.lastName }}</p>
                </template>

            </Card>
        </div>
        <div class="d-flex justify-content-center" v-else>
            <div class="spinner-border" role="status">
            </div>
        </div>
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name: "FriendComp",
    components: {
        Card
    },
    data() {
        return {
            friends: [
                {
                    id: 1,
                    firstName: 'James',
                    lastName: 'Peter',
                    gender: 'Male',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/profile-Image.png'
                },
                {
                    id: 2,
                    firstName: 'Joel',
                    lastName: 'Mukanya',
                    gender: 'Male',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/joel1.jpg'
                },
                {
                    id: 3,
                    firstName: 'Teddy',
                    lastName: 'Lukusa',
                    gender: 'Female',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/profile-Image.png'
                },
                {
                    id: 4,
                    firstName: 'Pierrot',
                    lastName: 'Kengela',
                    gender: 'Male',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/profile-Image.png'
                }
            ]
        }
    }

}
</script>

<style scoped>
.male {
    border: 2px solid gold;
    box-shadow: .3vw .2vw .5vw green;
}

.female {
    border: 2px solid pink;
    box-shadow: .3vw .2vw .5vw orange;
}
</style>