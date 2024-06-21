<script>
    import { onMount } from 'svelte';
    import {storeListProducts} from "../store/store.js";


    export let name = 'Home';
    let url = new URL("https://reqres.in/api/unknown");

    async function fetchData() {
        try {
            const request = await fetch(url, {
                headers: {
                    'Accept': 'application/json',
                }
            });
            const response = await request.json();
            storeListProducts.set(response.data);
        } catch (e) {
            console.log(e);
        }
    }

    onMount(() => {
        fetchData();
    });
    $: console.log($storeListProducts)
</script>

<h1>Welcome to the {name} page</h1>




    {#each $storeListProducts ?? [] as items}
        <tr class="mt-[30px]">
            <td>{items.id}</td>
            <td class="text-[{items.color}]">LOX {items.color}</td>
            <td class="">{items.name}</td>
            <td>{items.year}</td>
            <td>{items.pantone_value}</td>
        </tr>
    {/each}