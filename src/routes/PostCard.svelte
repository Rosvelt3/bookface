<script lang="ts">
	import { formatDistance } from 'date-fns';
	import { HeartIcon, MessageCircleIcon } from 'svelte-feather-icons';

	type Post = {
		username: string;
		date: string;
		text?: string;
		image?: string;
	};

	export let post: Post;

	const formattedDate = formatDistance(new Date(post.date), new Date(), { addSuffix: true });
</script>

<div class="card max-w-xl bg-base-200">
	<div class="card-body pb-4">
		<div class="flex items-center gap-3 mb-2">
			<div class="avatar">
				<div class="w-12 rounded-full">
					<img src="/testphoto.jpg" alt="" />
				</div>
			</div>
			<span class="text-primary-content font-medium">@{post.username}</span>
		</div>
		<div>
			<div class="text-secondary-content mb-2"><span>{post.text}</span></div>
			<div class="rounded-xl mb-2"><img class="rounded-xl" src="/testimage.jpg" alt="" /></div>
			<span>{formattedDate}</span>
		</div>
	</div>
	<div class="card-actions justify-center pb-2 px-2">
		<button class="btn btn-ghost normal-case gap-2 grow"><MessageCircleIcon /><span>Comment</span></button>
		<button class="btn btn-ghost normal-case gap-2 grow"><HeartIcon /><span>Like</span></button>
	</div>
</div>
