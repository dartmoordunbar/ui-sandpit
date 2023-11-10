
<script>

    const data = [
        {title: "Car Fire in Bournemouth", date:"23/5/2023"},
        {title: "Car fire in Staines", date:"21/7/2023"},
        {title: "Car Fire in Bournemouth", date:"23/5/2023"},
        {title: "Car fire in Staines", date:"21/7/2023"},
        {title: "Car Fire in Bournemouth", date:"23/5/2023"},
        {title: "Car fire in Staines", date:"21/7/2023"},
        {title: "Car Fire in Bournemouth", date:"23/5/2023"},
        {title: "Car fire in Staines", date:"21/7/2023"},
        {title: "Car Fire in Bournemouth", date:"23/5/2023"},
        {title: "Car fire in Staines", date:"21/7/2023"}
    ]

    let view = "grid"

    function toggle() {
        if(view == "grid"){
            view = "list"
        } else {
            view = "grid"
        }
    }
</script>


<div class="container mx-auto grid grid-cols-6 gap-10 py-10 font-light">
    <h1 class="text-3xl font-light">HO IMS Demo</h1>
    <div class="col-span-6 flex gap-5 border-b-2 pb-5">
        <button class="p-5 rounded font-bold text-white bg-[#732282]" on:click={() => toggle()}>Cards</button>
        <button class="p-5 rounded font-bold text-white bg-blue-400" on:click={() => toggle()}>List</button>
    </div>
    {#if view == "grid"}
        {#each data as data}
            <div class="col-span-2 bg-white rounded shadow-lg border-2 p-5">
                <h2 class="text-xl font-semibold">{data.title}</h2>
                <span>{data.date}</span>
            </div>
        {/each}
    {/if}
    {#if view == "list"}
        <table class="table table-auto col-span-6">
            <thead>
                <tr class="text-left w-1/4">
                    <th>Summary</th>
                    <th>Date</th>
                </tr>
            </thead>
            <tbody>
                {#each data as data}
                <tr>
                    <td>{data.title}</td>
                    <td>{data.date}</td>
                </tr>
                {/each}
            </tbody>
        </table>
    {/if}
</div>