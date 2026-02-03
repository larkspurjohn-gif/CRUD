<script>
</script>

<div class= "flex flex-col w-full h-full p-2">
    <div class= "w-full">
        <form 
            action="?/create"
            class="flex flex-col space-y-2 w-full items-center" 
            enctype="multipart/form-data"
        >
        <h3 class= "text-3xl font-bold">Tell us more about yourself</h3>
        <p class="mt-2 text-lg">We'll need first name, last name, and age</p>
        <div class="form-control w-full max-w-lg">
            <label for="first_name" class="block mb-2.5 text-sm font-medium text-heading">First name</label>
            <input type="text" id="first_name" class="bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand block w-full px-3 py-2.5 shadow-xs placeholder:text-body" required />
        </div>
        <div class="form-control w-full max-w-lg">
            <label for="last_name" class="block mb-2.5 text-sm font-medium text-heading">Last name</label>
            <input type="text" id="last_name" class="bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand block w-full px-3 py-2.5 shadow-xs placeholder:text-body" required />
        </div>
        <div class="form-control w-full max-w-lg">
            <label for="age" class="block mb-2.5 text-sm font-medium text-heading">Age</label>
            <input type="number" id="age" class="bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand block w-full px-3 py-2.5 shadow-xs placeholder:text-body" required />
        </div>
        <div class="w-full max-w-lg pt-3">
            <button type="submit" class="btn btn-primary w-full max-w-lg box-border border border-transparent hover:bg-brand-strong focus:ring-4 focus:ring-brand-medium shadow-xs font-medium leading-5 rounded-base text-sm px-4 py-2.5 bg-cyan-400">Create Information</button>
        </div>
        </form>
    </div>
</div>

