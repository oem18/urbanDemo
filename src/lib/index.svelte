<script>
import { goto } from '$app/navigation';
import Code from "./code.svelte";
import Header from "./header.svelte";

async function Switch(event) {
    console.log("Message", event.detail.text);
    await goto("/welcome");
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
    height: 70px;
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
    background-color: #eef3f8;
    background-color: #f1f2f2;
    border: 1px solid #000000c9;
    border-color: #dee0e1!important;
    border-radius: 10px;
    padding: 0 5px;
}

input {
    background-color: inherit;
    background-color: #eef3f8;
    background-color: #f1f2f2;
    outline: none;
    border: 0;
    width: 100%;
    height: 100%;
    padding: 0;
}

</style>
<section class="container">
    <section class="division">
        <Header />
    </section>
<section class="body">
    <section class="search">
        <input type="text" placeholder="*123#">
    </section>
</section>
    <section class="division">
        <Code on:message={Switch} code={"Next"} />
    </section>
</section>