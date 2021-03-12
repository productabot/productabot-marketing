<script lang="ts">
    import { onMount } from "svelte";
    let script;
    let password = "",
        confirmPassword = "";
    const params = new URLSearchParams(window.location.search);
    const username = params.get("username");
    const code = params.get("code");
    async function reset() {
        if (password !== confirmPassword) {
            alert("Make sure your passwords match");
        } else {
            let response = await fetch(
                `https://lambda.productabot.com/public/reset?username=${username}&code=${code}&password=${password}`
            );
            response = await response.json();
            console.log(response);
            alert("Password reset! You can log in the app now");
        }
    }
</script>

<main>
    <div style="margin-bottom: 20px;">reset password</div>
    <input bind:value={password} placeholder="password" />
    <input bind:value={confirmPassword} placeholder="confirm password" />
    <button on:click={reset} style="margin-top: 20px;">reset</button>
</main>

<style>
    main {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
        margin-top: 50px;
        font-size: 20px;
    }
    input {
        background-color: #000000;
        outline: none;
        border: none;
        border-bottom: 1px solid #ffffff;
        color: #ffffff;
        font-size: 20px;
        margin: 5px;
    }
    button {
        all: unset;
        background-color: #3f0054;
        padding: 5px 30px;
    }
</style>
