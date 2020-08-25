<script>
    let userName = '';
    let userEmail = '';
    let userPhone = '';
    let updatedUserPhone = '';

</script>

<h3>Form Input</h3>
<p>Name and Phone will update reactively, email demonstrates submitted</p>
<form on:submit|preventDefault={()=>updatedUserPhone=userPhone}>
    <label for="userName">Name</label>
    <input id="userName" type="text" placeholder='What is your name?' bind:value={userName}/>
    <label for="userEmail">E-mail</label>
    <input id="userEmail" type="text" placeholder="What is your email?"  bind:value={userEmail}/>
    <label for="userPhone">Phone</label>
    <input id="userPhone" type="text"  placeholder="What is your phone number?" bind:value={userPhone}/>
    <input type=submit value="Submit">
</form>
<!-- todo move output to it's own component useing store -->
<h3>Form Output</h3>
<p>Name: {userName}</p>
<p>Email: {userEmail}</p>
<p>Phone Number: {updatedUserPhone}</p>
