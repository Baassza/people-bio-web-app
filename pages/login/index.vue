<template>
    <v-container class="d-flex justify-center align-center" style="height: 90%;">
        <v-sheet class="mx-auto" width="500">
            <h3>Login</h3>
            <v-form fast-fail ref="form">
                <v-text-field class="my-2" v-model="UserName" :rules="UserNamerules" label="Username"></v-text-field>
                <v-text-field class="my-2" v-model="Password" :rules="Passwordrules" label="Password"></v-text-field>
                <v-btn class="my-2" @click="submit" block>Submit</v-btn>
            </v-form>
        </v-sheet>
    </v-container>
</template>

<script>
export default {
    data() {
        return {
            UserName: '',
            Password: '',
            UserNamerules: [
                v => !!v || 'Username is required',
                v => (v && v.length >= 3) || 'Username must be more than 3 characters',
            ],
            Passwordrules: [
                v => !!v || 'Password is required',
                v => (v && v.length >= 8) || 'Password must be more than 8 characters',
            ],
        }
    },
    methods: {
        submit(event) {
            event.preventDefault();
            if (this.$refs.form.validate()) {
                console.log("Username: ", this.UserName);
                console.log("Password ", this.Password);
            }
        }
    }
}
</script>

<style></style>