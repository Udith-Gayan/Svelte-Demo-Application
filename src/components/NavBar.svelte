<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();


    export let tabLabels;

    let selectedTabNumber = 1;
    let  activeClass = 'button-active';

    function clickTab(val) {
        selectedTabNumber = val;
        dispatch('tabPressed', {val: val});
    }
</script>

<div class="navbar">

    {#each tabLabels as tab}
        <button on:click={clickTab(tab.val)}  class={selectedTabNumber === tab.val ? activeClass : ''}>{tab.name}</button>
    {/each}


</div>

<style>
    .navbar {
        display: flex;
        background-color: rgba(0, 0, 255, 0);
        margin: -10px -30px 0 -30px;
        padding: 0 30px;
        box-shadow: 0px 3px 10px rgb(2, 2, 2);
    }


    button {
        min-height: 100%;
        display: inline;
        margin: 0 30px 0 0;
        font-size: 20px;
        font-weight: 600;
        color: #000000;
        background-color: #f4f4f400;
        outline: none;
        border: 0px;
        padding-top: 20px;
        padding-bottom: 20px;
    }

    .button-active {
        border-bottom: 5px solid rgb(0, 2, 1);
        /* transition: ease-in 800ms fade-out; */
    }

</style>