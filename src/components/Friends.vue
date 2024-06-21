<template>
    <div class="container">
        <div class="row">
            <h2 class="display-2">Best Friends</h2>
        </div>
        <div class="row gap-2" v-if="friends.length">
            <Card v-for="friend in friends" :key="friend.id">
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
                    profile: 'https://codjoelmayer.github.io/projectImages/images/profile-Image.png'
                },
                {
                    id: 2,
                    firstName: 'Joel',
                    lastName: 'Mukanya',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/joel1.jpg'
                },
                {
                    id: 3,
                    firstName: 'Teddy',
                    lastName: 'Lukusa',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/profile-Image.png'
                },
                {
                    id: 4,
                    firstName: 'Pierrot',
                    lastName: 'Kengela',
                    profile: 'https://codjoelmayer.github.io/projectImages/images/profile-Image.png'
                }
            ]
        }
    }

}
</script>

<style lang="scss" scoped></style>