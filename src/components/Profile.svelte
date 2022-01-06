<script>
    import { user } from "../stores";
    import { useFocus } from "svelte-navigator";
    
	const registerFocus = useFocus();
    function handleLogout() {
        $user = null;
    }
</script>

<div class="bg-blue-300 px-2 py-3">
    <h1>Profile page</h1>
    <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam libero nulla, blandit in placerat in, dictum in massa. Morbi dignissim neque lacus, sit amet pulvinar augue fermentum at. Etiam pellentesque imperdiet mi sed dapibus. Etiam luctus augue enim, sed gravida magna dictum sed. Fusce non eros justo.</p>
    <h3 use:registerFocus>Welcome {$user.username}</h3>
    <button on:click={handleLogout}>Logout</button>
</div>