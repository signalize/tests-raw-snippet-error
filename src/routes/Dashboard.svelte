<script>
    let {children, component} = $props();
</script>
    {@render component()}
<div>
    {@render component()}
    ---
    {@render children()}
</div>
