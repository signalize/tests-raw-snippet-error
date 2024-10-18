<script>
    import {createRawSnippet, hydrate} from 'svelte';
    import {render} from 'svelte/server';
    import Child from '../Child.svelte';
    import {browser} from "$app/environment";


    const props = $state({value: 'Test'});
    const hello = createRawSnippet(() => ({
        render: () => `
 			<div>${browser ? '' : render(Child, {props}).body}</div>
 		`,
        setup(target) {
            hydrate(Child, {target, props})
        }
    }));
</script>

You 'think' this works.... But please refresh your browser now....
<div>
{@render hello()}
</div>