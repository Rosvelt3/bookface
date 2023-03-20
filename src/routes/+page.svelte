<script>
	import Header from './Header.svelte';
	import PostCard from './PostCard.svelte';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<Header />
	<div class="flex container justify-between pt-6">
		<div />
		<div class="flex flex-col items-center gap-8">
			<PostCard
				post={{
					username: 'Test User',
					date: '2021-01-01 12:00:00',
					text: 'This is a test post'
				}}
			/>
			<PostCard
				post={{
					username: 'Test User',
					date: '2023-01-01 12:00:00',
					text: 'This is a test post'
				}}
			/>
			<PostCard
				post={{
					username: 'Test User',
					date: '2023-01-01 12:00:00',
					text: 'This is a test post'
				}}
			/>
			<PostCard
				post={{
					username: 'Test User',
					date: '2022-01-01 12:00:00',
					text: 'This is a test post'
				}}
			/>
		</div>
		<div class="relative">
			<div class="flex flex-col gap-2 fixed">
				<h2 class="text-lg font-medium">Friends</h2>
				<div class="flex flex-col gap-4">
					<div class="flex gap-2 items-center">
						<div class="avatar">
							<div class="w-10 rounded-full">
								<img src="/testphoto.jpg" alt="Your Avatar" />
							</div>
						</div>
						<span class="font-medium">Test User</span>
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
