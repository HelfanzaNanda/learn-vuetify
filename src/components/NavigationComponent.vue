<template>
    <div>
        <v-app-bar flat app color="blue-grey lighten-4">
            <v-app-bar-nav-icon
                class="blue-grey--text d-none d-md-flex"
                @click="drawer = !drawer"
            ></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase blue-grey--text">
                <span class="font-weight-light">E</span>
                <span> Maji</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn
                depressed
                color="blue-grey lighten-4 blue-grey--text d-none d-md-flex"
            >
                <span>sign out</span>
                <v-icon right>exit_to_app</v-icon>
            </v-btn>
        </v-app-bar>

        <v-navigation-drawer
            app v-model="drawer"
            class="blue-grey darken-2 d-none d-md-flex"
        >
            <v-list class="mt-16">
                <v-list-item-group>
                    <v-list-item
                        v-for="(item, i) in items"
                        :key="i"
                        router
                        :to="item.route"
                    >
                        <v-list-item-icon>
                            <v-icon
                                class="white--text"
                                v-text="item.icon"
                            ></v-icon>
                        </v-list-item-icon>
                        <v-list-item-content>
                            <v-list-item-title
                                class="white--text caption"
                                v-text="item.text"
                            ></v-list-item-title>
                        </v-list-item-content>
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>

        <v-bottom-navigation :value="value" color="blue-grey darken-2" app class="d-flex d-md-none">
            <v-btn v-for="(item, index) in items" :key="index" router :to="item.route">
                <span>{{ item.text }}</span>
                <v-icon>{{ item.icon }}</v-icon>
            </v-btn>

            <v-btn router to="logout">
                <span>Sign Out</span>
                <v-icon>exit_to_app</v-icon>
            </v-btn>
        </v-bottom-navigation>
    </div>
</template>

<script>
export default {
    data: () => {
        return {
            value : 1,
            drawer: false,
            items: [
                { icon: "dashboard", text: "Dashboard", route: "/" },
                { icon: "next_week", text: "Tool", route: "/tool" },
                { icon: "people", text: "User", route: "/user" },
                { icon: "person", text: "Profile", route: "/profile" },
            ],
        };
    },
};
</script>