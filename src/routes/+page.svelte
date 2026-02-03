<script>
  let infos = [];
  let firstName = '';
  let lastName = '';
  let age = '';
  let edit = null;
  let uniqueId = 0;

  function newUniqueID(){
    uniqueId ++;
  }
  function addInfo (){
    if (edit === null){
    newUniqueID();
    infos = [...infos, {
      uniqueId,
      firstName,
      lastName,
      age
    }];
    console.log(infos);
  }else{
    infos = infos.map(info =>
      info.uniqueId === edit
        ? { ...info, firstName, lastName, age }
        : info
    );

  }

    resetForm();
  }

  function resetForm(){
    firstName = '';
    lastName = '';
    age = '';
    edit = null;
  }

  function editInfo(info){
    firstName = info.firstName;
    lastName = info.lastName;
    age = info.age;
    edit = info.uniqueId;
  }

  function deleteInfo(infoId){
    infos = infos.filter(info => info.uniqueId !==infoId);
  }
</script>

<div class= "flex flex-col w-full h-full p-2">
    <div class= "w-full">
        <form 
            class="flex flex-col space-y-2 w-full items-center" 
            enctype="multipart/form-data"
            on:submit|preventDefault= {addInfo}
        >
        <h3 class= "text-3xl font-bold">Tell us more about yourself</h3>
        <p class="mt-2 text-lg">We'll need first name, last name, and age</p>
        <div class="form-control w-full max-w-lg">
            <label for="first_name" class="block mb-2.5 text-sm font-medium text-heading">First name</label>
            <input type="text" id="first_name" class="bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand block w-full px-3 py-2.5 shadow-xs placeholder:text-body" required bind:value={firstName}/>
        </div>
        <div class="form-control w-full max-w-lg">
            <label for="last_name" class="block mb-2.5 text-sm font-medium text-heading">Last name</label>
            <input type="text" id="last_name" class="bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand block w-full px-3 py-2.5 shadow-xs placeholder:text-body" required bind:value={lastName}/>
        </div>
        <div class="form-control w-full max-w-lg">
            <label for="age" class="block mb-2.5 text-sm font-medium text-heading">Age</label>
            <input type="number" id="age" class="bg-neutral-secondary-medium border border-default-medium text-heading text-sm rounded-base focus:ring-brand focus:border-brand block w-full px-3 py-2.5 shadow-xs placeholder:text-body" required bind:value={age}/>
        </div>
        <div class="w-full max-w-lg pt-3">
            <button type="submit" class="btn btn-primary w-full max-w-lg box-border border border-transparent hover:bg-brand-strong focus:ring-4 focus:ring-brand-medium shadow-xs font-medium leading-5 rounded-base text-sm px-4 py-2.5 bg-cyan-400"> {edit ? 'Update' : 'Add Information'} </button>
        </div>
        </form>
    </div>
    <div class= "w-full">
    <!--TABLE-->
    <table class= "w-full border-collapse border border-gray-300">
      <thead class="bg-gray-100">
        <tr> 
          <th class="border p-2">ID</th>
          <th class="border p-2">First Name</th>
          <th class="border p-2">Last Name</th>
          <th class="border p-2">Age</th>
        </tr>
      </thead>
      <tbody>
        {#each infos as info}
        <tr class="text-center">
          <td class="border p-2">{info.uniqueId}</td>
          <td class="border p-2">{info.firstName}</td>
          <td class="border p-2">{info.lastName}</td>
          <td class="border p-2">{info.age}</td>
          <td class="border p-2 space-x-2">
            <button on:click={()=> editInfo(info)} class="bg-yellow-400 px-3 py-1 rounded hover:bg-yellow-500">
              Edit
            </button>
            <button on:click={()=> deleteInfo(info.uniqueId)} class="bg-red-400 px-3 py-1 rounded hover:bg-red-500">
              Delete
            </button>
          </td>
        </tr>
        {/each}
      </tbody>
    </table>
    </div>
</div>

  