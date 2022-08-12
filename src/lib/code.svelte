<script>
import { createEventDispatcher } from 'svelte';
export let code;
export let data;

const dispatch = createEventDispatcher();

function Clicked() {
    dispatch('message', {
        text: data
    });
}

</script>
<style>

section.container {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    width: 90%;
    height: 45px;
    border: 1px solid #000000c9;
    border-color: #dee0e1!important;
    background-color: #ff385c;
    background-color: #049d02;
    border-radius: 10px;
    cursor: pointer;
}

p {
    display: flex;
    flex-flow: row nowrap;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    border-radius: 10px;
    color: #ffffff;
    font-weight: 600;
    font-size: 1rem;
    cursor: pointer;
}

</style>
<section on:click={Clicked} class="container">
    <p>
        {code}
    </p>
</section>