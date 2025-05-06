<script>
    export let icon = "github";
    export let size = 32;
    export let color = "";
</script>

<img
    src={`https://cdn.simpleicons.org/${icon}${color ? "/" + color : ""}`}
    alt={icon}
    width={size}
    height={size}
/>
