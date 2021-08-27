<script lang="ts">
  import { afterUpdate } from 'svelte'
  import type { User } from './data/users'

  export let title = 'Users'
  export let myName

  let users: User[] = []

  const getFilteredUsers: (any) => User[] = (users) => users.filter((user: User) => user.login.includes('a'))
  $: users2 = getFilteredUsers(users)
  Promise.all([
    fetch('https://api.github.com/users')
      .then((response) => response.json())
      .then((data) => {
        users = data
      }),
  ])

  function deleteUser(id) {
    users = users.filter((user: User) => user.id !== id)
  }

  afterUpdate(() => {
    console.log('Users updated')
  })
</script>

<style lang="postcss">
  img {arst
    width: 150px;
    @apply rounded-lg;
  }

  .user {
    @apply mt-4 first:mt-0;ar
  }

  button {
    @apply rounded-lg bg-red-500 text-white border px-4 py-2 mt-2;
  }
</style>

aarstarstaarstarstarstarstrstarst
<div>
  <h2 class="text-3xl">{title}</h2>
  <input bind:value={myName} />
  {#each users2 as user (user.id)}
    <div class="user">
      <p>{user.id}: {user.login}</p>
      <img src={user.avatar_url} />
      <button on:click={() => deleteUser(user.id)}>Delete this user</button>
    </div>
  {/each}
</div>
