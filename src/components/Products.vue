<template>
    <div class="container">
        <div class="row">
            <h2 class="display-2">Products</h2>
        </div>
        <div class="row gap-2 justify-content-center">
            <Card v-for="product in products" :key="product.id">
                <template #cardHeader>
                    <img :src="product.image" :alt="product.make" class="img-fluid" loading="lazy">
                </template>
                <template #cardBody>
                    <p>{{ product.make }} </p>
                    <p>Amount: R{{ product.amount }}</p>
                    <p>{{ product.spec }}</p>
                </template>
            </Card>
        </div>
    </div>
</template>

<script>
import Card from './Card.vue'
export default {
    name: "ProductComp",
    components: {
        Card
    },
    data() {
        return {
            products: [
                {
                    id: 1,
                    make: "Dell",
                    spec: "Latitude-E5450 i3 5th, HDD 1TB, RAM 16GB, Operating System Windows 11 Business",
                    amount: 25000.00,
                    image: "https://i.postimg.cc/65tcMqdc/Dell-Latitude-E5450-i3-5th-GEN-1-for-business-10000.jpg"
                },
                {
                    id: 2,
                    make: "Acer",
                    spec: "Extensa 15.6 inch, SSD 256GB, RAM 8GB, Operating System Windows 10 Home",
                    amount: 6240.00,
                    image: "https://i.postimg.cc/gJKtZmp1/Acer-Extensa-15-6-inch-256-GBSSd-8-GBRAM.png"
                },
                {
                    id: 3,
                    make: "Acer",
                    spec: "Travel Mate Intel Core i5, SSD 512GB, RAM 8GB, Operating System Windows 10 Pro",
                    amount: 10000.00,
                    image: "https://i.postimg.cc/0j2WGF2j/Acer-Travel-Mate-Intel-Corei5-SSD512-8-GBRAM.png"
                },
                {
                    id: 4,
                    make: "Lenovo",
                    spec: "Idea Pad Intel Celeron, HDD 1TB, RAM 4GB, Operating System Windows 10 Home",
                    amount: 6350.00,
                    image: "https://i.postimg.cc/rwwdXLQg/Lenovo-IDea-Pad-1-TBHDD-4-GBRAM-6350.png"
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped></style>