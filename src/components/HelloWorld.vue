<template>
    <div class="header">
        <div class="text">{{ msg }}</div>
    </div>
    <div class="login">
        <h3>Log in</h3>
        <form class="maj" action="">
            <p>
                <input type="text" placeholder="First Name" name="First Name" />
            </p>
            <p>
                <input type="text" placeholder="Last Name" name="Last Name" />
            </p>
            <p><input type="email" placeholder="Your Email" name="email" /></p>
            <p>
                <input
                    type="password"
                    placeholder="Your Password"
                    name="Password"
                />
            </p>
            <p>
                <input type="number" placeholder="Your Nnmber" name="number" />
            </p>
            <p>
                <input type="submit" value="Send" />
            </p>
        </form>
    </div>
    <div class="footer">Welcome in our world</div>
</template>

<script>
export default {
    name: "HelloWorld",
    props: {
        msg: String,
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.header {
    position: relative;
    height: 600px;
    margin-bottom: 20px;
    background-image: url(../imags/484253.jpg);
    background-size: cover;
}
.text {
    color: white;
    font-weight: bold;
    z-index: 3;
    text-align: center;
    font-size: 30px;
    padding-top: 250px;
}
.login {
    margin-top: 20px;
    margin-bottom: 20px;
    background-image: url(../imags/6464-2.png);
    background-size: cover;
    padding-bottom: 20px;
    h3 {
        padding-top: 20px;
        font-weight: bold;
    }
}
.footer {
    background-color: aqua;
    text-align: center;
}
</style>
