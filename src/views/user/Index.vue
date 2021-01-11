<template>
    <div>
        <v-row>
            <v-col cols="12" sm="12" md="4">
                <v-card elevation="2" shaped>
                    <div class="pa-2">
                        <div class="ml-2 title text-capitalize">
                            tambah user
                        </div>
                        <v-form ref="form" class="pa-2">
                            <v-text-field
                                v-model="form.name"
                                label="Nama"
                                required
                            ></v-text-field>
                            <v-text-field
                                v-model="form.email"
                                label="E-mail"
                                required
                            ></v-text-field>
                            <v-select
                                v-model="form.role"
                                label="Role"
                                required
                                :items="itemRoles"
                            ></v-select>
                            <v-btn
                                small
                                color="grey darken-2"
                                class="mr-4 white--text"
                                @click="validate"
                                >tambah</v-btn
                            >
                            <v-btn small color="warning" class="white--text"
                                >reset</v-btn
                            >
                        </v-form>
                    </div>
                </v-card>
            </v-col>

            <v-col cols="12" sm="12" md="8">
                <v-card elevation="2" tile>
                    <div class="pa-3 title text-capitalize">data user</div>

                    <v-card flat class="clas pa-3">
                        <v-row v-for="(user, index) in users" :key="index">
                            <v-col cols="12" sm="12" md="3">
                                <div class="caption grey--text">Nama</div>
                                <div class="caption">{{ user.name }}</div>
                            </v-col>

                            <v-col cols="12" sm="12" md="3">
                                <div class="caption grey--text">Email</div>
                                <div class="caption" >{{ user.email }}</div>
                            </v-col>

                            <v-col cols="12" sm="12" md="3">
                                <div class="caption grey--text">Role</div>
                                <div class="caption" >{{ user.role }}</div>
                            </v-col>
                            <v-col cols="12" sm="12" md="3">
                                <div class="caption grey--text text-md-center">Action</div>
                                <div class="text-md-center">
                                    <v-btn elevation="2" class="fab blue-grey darken-1 mr-2 white--text" fab x-small><v-icon>edit</v-icon></v-btn>
                                    <v-btn elevation="2" class="fab blue-grey darken-3 white--text" fab x-small><v-icon>delete</v-icon></v-btn>
                                </div>
                            </v-col>
                            <v-divider cols="12"></v-divider>
                        </v-row>
                    </v-card>
                </v-card>
            </v-col>
        </v-row>
    </div>
</template>

<script>
export default {
   
    data: () => ({
        users: [
            { name: "admin", email: "admin@example.com", role: "admin" },
            { name: "pengawas", email: "pengawas@example.com", role: "pengawas", },
            { name: "penguji", email: "penguji@example.com", role: "penguji" },
        ],
        form: { name: "", email: "", role: "" },
        itemRoles: ["pengawas", "penguji"],
    }),
    methods: {
        validate() {
            this.$refs.form.validate();
        },
    },
};
</script>