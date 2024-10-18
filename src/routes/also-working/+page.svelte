<script>
    import {createRawSnippet, hydrate} from 'svelte';
    import Child from '../Child.svelte';


    const props = $state({value: 'Test'});
    const hello = createRawSnippet(() => ({
        render: () => `
 			<div></div>
 		`,
        setup(target) {
            hydrate(Child, {target, props})
        }
    }));
</script>

<div>
    {@render hello()}
</div>