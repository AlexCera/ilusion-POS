<template>
    <v-navigation-drawer v-model="drawer" color="#2B2B2B" class="">
        <div class="pa-4">
            <v-img
                src="https://raw.githubusercontent.com/zakaria-29-dev/Restaurant-Food-Ordering-Dashboard-Design/main/public/p1.webp"
                width="160" height="160" class="ml-9"></v-img>
        </div>
        <!--  -->
        <v-card class="rounded-e-xl me" width="60" height="400" color="#545454"></v-card>
        <!-- navigation -->
        <v-list class="top">
            <v-list-item v-for="(item, index) in navigation" :key="index" :value="item" class="mb-4" color="#FF6259"
                variant="plain">
                <template v-slot:append="{ isActive }">
                    <div v-if="isActive" class="a"></div>
                </template>
                <template v-slot:prepend>
                    <v-icon :icon="item.icon"></v-icon>
                </template>
                <v-list-item-title v-text="item.name"></v-list-item-title>
            </v-list-item>
        </v-list>
        <!-- Settings and Notifications -->
        <v-div
            style="position: absolute; bottom: 20px; margin-left: auto;margin-right: auto; left: 0; right: 0; text-align: center;">
            <v-btn icon="mdi mdi-cog" size="small" class="mr-2" color="#5F3B39"></v-btn>

            <v-badge dot color="#FF6259">
                <v-btn icon="mdi mdi-bell" size="small" color="#5F3B39"></v-btn>
            </v-badge>

        </v-div>
    </v-navigation-drawer>
</template>

<script setup>
import { ref } from "vue";
const navigation = [
    { name: "Dashboard", icon: "mdi mdi-view-dashboard" },
    { name: "Orders", icon: "mdi mdi-phone-classic" },
    { name: "Restaurants", icon: "mdi mdi-map-marker-radius" },
    { name: "Finance", icon: "mdi mdi-finance" },
    { name: "Logout", icon: "mdi mdi-logout" },
];

const drawer = ref(null);
</script>

<script>
export default {
    data: () => ({
        cards: ["Today", "Yesterday"],
        drawer: null,
    }),
};
</script>

<style scoped>
.v-list-item.v-list-item--active.v-list-item--link.border.v-theme--light.text-red.v-list-item--density-default.v-list-item--one-line.v-list-item--variant-text {
    color: white !important;
}

.top {
    margin-top: 60px;
}

.me {
    position: absolute;
    margin-top: 28px;
}

.v-locale--is-ltr .rounded-e-xl {
    border-top-right-radius: 44px !important;
    border-bottom-right-radius: 44px !important;
}

.a {
    top: 32%;
    left: 20.5%;
    position: absolute;
    height: 15px;
    width: 15px;
    background: linear-gradient(-90deg, #545454, #545454 50%, black 50%);
    border-radius: 50%;
}
</style>