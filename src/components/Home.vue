<template>
    <v-app is="inspire" :style="{ background: $vuetify.theme.themes.light.colors.primary }">

        <!-- ***** START COMPONENT => SIDEBAR ***** -->
        <Sidebar />
        <!-- ***** END COMPONENT => SIDEBAR ***** -->

        <v-main>
            <v-container>
                <v-row>
                    <v-col cols="12" sm="12">
                        <!-- search bar -->
                        <v-text-field density="compact" placeholder="Search your favorite store, food or dishes ..."
                            append-inner-icon="mdi-magnify" variant="outlined" rounded
                            class="text-grey mx-8"></v-text-field>
                        <!-- toolbar -->
                        <v-toolbar color="transparent" class="pr-1 mt-n7">
                            <v-toolbar-title class="text-white">Categories</v-toolbar-title>
                            <v-spacer></v-spacer>
                            <span class="text-caption text-white">View all</span>
                            <v-btn density="compact" icon="mdi mdi-chevron-right-box" color="red"></v-btn>
                        </v-toolbar>
                        <!-- text categories info -->
                        <h6 class="text-white ml-4 mt-n4">
                            <span class="text-red">5+ new</span> categories added this month
                        </h6>
                        <!-- categories -->
                        <div class="d-flex justify-space-evenly mt-4" color="transparent">
                            <v-avatar v-for="(cat, index) in foodCategories" :key="index" :title="cat.name"
                                color="#605850" size="75">
                                <v-img :src="cat.image" height="50"></v-img>
                            </v-avatar>
                        </div>
                        <!-- text dishes info -->
                        <v-toolbar color="transparent" class="pr-1 mt-3">
                            <v-toolbar-title class="text-white">Popular Dishes</v-toolbar-title>
                            <v-spacer></v-spacer>
                            <span class="text-caption text-white">View More</span>
                            <v-btn density="compact" icon="mdi mdi-chevron-right-box" color="grey"></v-btn>
                        </v-toolbar>
                        <h6 class="text-white ml-4 mt-n4">
                            <span class="text-red">2+ new </span> dishes added this week
                        </h6>
                        <div class="d-flex justify-space-evenly mt-4" color="transparent">
                            <v-card color="transparent" v-for="(dish, index) in dishes" :key="index">
                                <v-img height="70" :src="dish.image" class="imag"></v-img>
                                <v-card class="mt-n10" width="150" color="#303030">
                                    <v-card-item class="text-center">
                                        <v-card-title class="mt-10">{{ dish.name }}</v-card-title>
                                        <v-card-subtitle>
                                            <span class="me-1">Starting From</span>
                                        </v-card-subtitle>
                                        <v-card-title>{{ dish.money }}</v-card-title>
                                    </v-card-item>
                                    <v-card-text>
                                        <v-row align="center" class="mx-0">
                                            <v-icon color="yellow" icon="mdi mdi-star" size="small"></v-icon>
                                            <div class="text-grey ms-4">
                                                <h6>{{ dish.star }}</h6>
                                            </div>
                                            <v-spacer></v-spacer>
                                            <div class="text-grey ms-4">
                                                0
                                                <h5>Total Sale</h5>
                                            </div>
                                        </v-row>
                                    </v-card-text>
                                </v-card>
                            </v-card>
                        </div>
                        <!-- text orders info -->
                        <v-toolbar color="transparent" class="pr-1 mt-n2">
                            <v-toolbar-title class="text-white">Order Report</v-toolbar-title>
                            <v-spacer></v-spacer>
                            <span class="text-caption text-white">View all</span>
                            <v-btn density="compact" icon="mdi mdi-chevron-right-box" color="grey"></v-btn>
                        </v-toolbar>
                        <h6 class="text-white ml-4 mt-n4">
                            <span class="text-red">Awesome 50+ new </span> orders got this week
                        </h6>
                        <v-card class="rounded-xl ma-2 pa-1" color="#424343">
                            <v-row>
                                <v-col cols="12" sm="1"></v-col>
                                <v-col cols="12" sm="2" class="text-center">
                                    <span class="text-caption">Customer</span>
                                </v-col>
                                <v-col cols="12" sm="2" class="text-center">
                                    <span class="text-caption">Order Number</span>
                                </v-col>
                                <v-col cols="12" sm="2" class="text-center">
                                    <span class="text-caption">Address</span>
                                </v-col>
                                <v-col cols="12" sm="2" class="text-center">
                                    <span class="text-caption">Amount</span>
                                </v-col>
                                <v-col cols="12" sm="2" class="text-center">
                                    <span class="text-caption">Status</span>
                                </v-col>
                                <v-col cols="12" sm="1"></v-col>
                            </v-row>
                        </v-card>

                        <v-row>
                            <v-col cols="12" sm="3" class="text-center">
                                <v-avatar>
                                    <v-img
                                        src="https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/20.jpg?raw=true"></v-img>
                                </v-avatar>
                                <span class="text-caption text-white ml-2">Jhon Doe</span>
                            </v-col>
                            <v-col cols="12" sm="2" class="text-center mt-2">
                                <span class="text-caption text-white ml-2">11998800</span>
                            </v-col>
                            <v-col cols="12" sm="2" class="text-center mt-2">
                                <span class="text-caption text-white ml-2">Pto Gaita</span>
                            </v-col>
                            <v-col cols="12" sm="2" class="text-center mt-2">
                                <span class="text-caption text-white ml-2">$35.000</span>
                            </v-col>
                            <v-col cols="12" sm="2">
                                <v-chip variant="flat" color="success" class="text-caption">Completed</v-chip>
                            </v-col>
                            <v-col cols="12" sm="1" class="text-center"></v-col>
                        </v-row>
                    </v-col>

                    <!-- cart resume -->

                </v-row>
            </v-container>
        </v-main>

    </v-app>
</template>

<script setup>
import Sidebar from '@/components/Sidebar.vue';

const foodCategories = [
    { name: "Burger", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/2.png?raw=true" },
    { name: "Pizza", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/3.png?raw=true" },
    { name: "Pizza Slice", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/4.png?raw=true" },
    { name: "Burritos", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/5.png?raw=true" },
    { name: "Tacos", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/6.png?raw=true" },
    { name: "Cake", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/7.png?raw=true" },
    { name: "Lasagna", image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/8.png?raw=true" },
];
const dishes = [
    { image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/11.png?raw=true", name: "Chicken Burger", money: "$10.000", star: "4.5" },
    { image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/22.png?raw=true", name: "Peperoni Pizza", money: "$22.000", star: "4.1" },
    { image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/33.png?raw=true", name: "Sushi", money: "$15.000", star: "4.3" },
    { image: "https://github.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/blob/main/public/44.png?raw=true", name: "Gratin", money: "$23.000", star: "4.9" },
];
</script>


<style scoped>
.mRight {
    margin-right: 100px;
}

.v-list {
    background: transparent !important;
}

.mLeft {
    margin-left: 90px;
}

.imag {
    z-index: 9999 !important;
}
</style>