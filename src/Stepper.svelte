<script>
    export let value;
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    const dispatchValue = (btnValue)=>{
        dispatch('btnValue', {
            value: btnValue
        });
    }
</script>

<main>
	<button on:click={() => dispatchValue('-')}>-</button>
    <h1>{value}</h1>
	<button on:click={() => dispatchValue('+')}>+</button>
</main>

<style>
	main{
        display: flex;
        justify-content: center;
        align-items: center
    }

    button{
        border: 1px gray solid;
        height: 40px;
        width: 40px;
        border-radius: 25%;
        font-weight: bolder;
        margin: 5px;
    }
</style>