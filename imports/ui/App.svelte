<script>
    import { useTracker } from "meteor/rdb:svelte-meteor-data";
    import { Records } from "../api/records";

    $: records = useTracker(() => Records.find({}).fetch());
</script>

<header>
    <h1>Hello New Normal!</h1>
    {#each $records as record}
        <h2>{record.title}</h2>
    {/each}
</header>