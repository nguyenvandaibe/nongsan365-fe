<template>
    <div class="row justify-content-center">
        <div class="col-sm-4">
            <div class="card shadow">
                <div class="card-body">
                    <form @submit.prevent="submit">
                        <div class="mb-3">
                            <label for="username">Tên đăng nhập</label>
                            <input
                                type="text"
                                class="form-control"
                                v-model="form.username"
                            />
                        </div>

                        <div class="mb-3">
                            <label for="password">Mật khẩu</label>
                            <input
                                type="password"
                                name="password"
                                id="password"
                                class="form-control"
                                v-model="form.password"
                            />
                        </div>

                        <button type="submit" class="btn btn-primary">
                            Đăng nhập
                        </button>
                    </form>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            form: {
                username: "",
                password: "",
            },
        };
    },
};
</script>