<script lang="ts">
	import { page } from '$app/stores';
	import { HomeIcon, UsersIcon, UserIcon, SettingsIcon, LogOutIcon } from 'svelte-feather-icons';
  
	const routes = [
		{
			icon: HomeIcon,
			name: 'Home',
			path: '/'
		},
		{
			icon: UsersIcon,
			name: 'Friends',
			path: '/friends'
		}
	] as const;

	const menuItems = [
		{
			icon: UserIcon,
			name: 'Profile',
			path: '/profile'
		},
		{
			icon: SettingsIcon,
			name: 'Settings',
			path: '/settings'
		},
		{
			icon: LogOutIcon,
			name: 'Logout',
			path: '/logout'
		}
	] as const;
</script>

<header class="sticky top-0 z-50 bg-base-200">
	<div class="container">
		<nav class="navbar ">
			<div class="navbar-start">
				<div class="btn btn-ghost normal-case text-xl">
					<a href="/">Bookface</a>
				</div>
			</div>
			<div class="navbar-center tabs">
				{#each routes as { name, icon, path }}
					<a
						class="btn btn-ghost normal-case text-xl"
						class:text-secondary={$page.url.pathname === path}
						href={path}
						aria-label={name}
					>
						{#if icon}
							<svelte:component this={icon} />
						{/if}
					</a>
				{/each}
			</div>
			<div class="navbar-end">
				<div class="dropdown dropdown-end">
					<button tabindex="0" class="btn btn-ghost btn-circle avatar">
						<div class="w-10 rounded-full">
							<img src="/testphoto.jpg" alt="Your Avatar" />
						</div>
					</button>
					<ul
						tabindex="0"
						role="button"
						class="mt-3 p-2 shadow menu menu-compact dropdown-content bg-base-200 rounded-box w-52"
					>
						{#each menuItems as { name, icon, path }}
							<li>
								<a href={path} class="text-base">
									{#if icon}
										<svelte:component this={icon} />
									{/if}
									{name}
								</a>
							</li>
						{/each}
					</ul>
				</div>
			</div>
		</nav>
	</div>
</header>
