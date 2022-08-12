<script>
import { goto } from '$app/navigation';
import Code from "./code.svelte";
let value = "";
async function Switch(event) {
    // console.log("Message", event.detail.text);
    if(value == "00") await goto("/welcome");
    else if(value.length > 0 && value.match(/[0-9]+/)) {
        localStorage.setItem("amount", value);
        await goto("/confirmation");
    }
}

</script>
<style>

section.container {
    display: flex;
    flex-flow: column nowrap;
    justify-content: space-between;
    align-items: center;
    width: 350px;
    height: 600px;
    background-color: #ffffff;
    box-shadow: 0 1px 2px 0 rgb(60 64 67 / 30%), 
    0 1px 3px 1px rgb(60 64 67 / 15%);
    padding: 15px;
}

section.division {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    min-height: 70px;
    width: 100%;
}

section.body {
    height: 50%;
    width: 100%;
}

section.search {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 40px;
    /* background-color: #eef3f8;
    background-color: #f1f2f2; */
    border-bottom: 1px solid #000000c9;
    /* border-color: #dee0e1!important; */
    /* border-radius: 10px; */
    padding: 0 5px;
    margin-top: 15px;
}

input {
    background-color: inherit;
    /* background-color: #eef3f8;
    background-color: #f1f2f2; */
    outline: none;
    border: 0;
    width: 100%;
    height: 100%;
    padding: 0;
}

section.name {
    display: flex;
    flex-flow: column nowrap;
    justify-content: center;
    align-items: flex-start;
    width: 100%;
    height: 100%;
    padding: 15px 0;
}

section.name h2 {
    margin: 0;
    color: #1c1c1c;
    color: #2a2c2d;
    color: #049d02;
    font-weight: 900;
    font-size: 1.8rem;
}

ul {
    display: flex;
    flex-flow: column nowrap;
    justify-content: flex-start;
    align-items: flex-start;
    list-style: none;
    height: auto;
    width: 100%;
    margin: 0;
    padding: 0;
}

li {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    font-size: 1.1rem;
    font-weight: 600;
    height: 100%;
    color: #2a2c2d;
    margin-bottom: 15px;
}

a {
    width: 100%;
    height: 100%;
    color: #000000;
    color: #2a2c2d;
}

</style>
<section class="container">
    <section class="division">
        <section class="name">
            <h2>Please enter the amount you want to send.</h2>
        </section>
    </section>
    <section class="body">
        <ul>
            <li>
                <a class="bar" href="/">
                    00> Back to main menu
                </a>
            </li>
        </ul>
        <section class="search">
            <input bind:value type="text" placeholder="">
        </section>
    </section>
    <section class="division">
        <Code on:message={Switch} code={"Send"} />
    </section>
</section>