<template>
    <div class="form">
        <form @submit.prevent="submitEvent">
            <div>
                <label for="name"> Name:</label>
                <input id="name" type="text" v-model="user.name" />
                <span class="error" v-if="errors.name">{{ errors.name }}</span>
            </div>
            <div>
                <label for="email">Email:</label>
                <input id="email" type="email" v-model="user.email" />
                <span class="error" v-if="errors.email">
                    {{ errors.email }}</span
                >
            </div>
            <div>
                <button type="submit">Submit</button>
            </div>
        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                user: {
                    name: '',
                    email: ''
                },
                errors: {}
            }
        },
        methods: {
            submitEvent() {
                this.errors = {}
                if (!this.user.name) {
                    this.errors.name = 'Name is required'
                }
                if (!this.user.email) {
                    this.errors.email = 'Email is required'
                }
                if (!Object.keys(this.errors).length) {
                    // form is valid, you can submit it here
                    print('succeed')
                }
            }
        }
    }
</script>

<style scoped>
    form {
        display: flex;
        flex-direction: column;
        row-gap: 20px;
    }

    button {
        width: 80px;
        background-color: rgb(24, 151, 24);
        color: white;
    }
    .error {
        color: red;
    }
</style>
