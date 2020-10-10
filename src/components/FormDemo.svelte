<script>

   export let title;
   export let firstname = '' ;
   export let lastname = '';
   $: fullName = firstname + ' ' + lastname;
   export let dob;
   export let university = '';

</script>


<div class="headingRow">
    <h1>{title}</h1>
</div>

<div class="formRow">
    <div class="col1">
       First Name:  <input type="text" bind:value={firstname} />
       <br />
       Last Name:   <input type="text" bind:value={lastname} />
       <br />
       Date of Birth: <input type="date" bind:value={dob} />
       <br />
       University: <input type="text" bind:value={university} />
    </div>
    <div class="col2">
        <b>Full Name :</b> {fullName}
        <br /><br />
        <b>Date of Birth :</b> {dob}
        <br /><br />
        <b>Current University :</b> {university}
    </div>
</div>

<style>
    .headingRow {
        display: flex;
        justify-content: center;
        color: #ffff;
    }

    .formRow {
        display: flex;
        width: 100%;
        height: 100vh;
    }

    .formRow > div {
        width: 50%;
        height: 100%;
    }

    .formRow {
        display: flex;
    }
</style>