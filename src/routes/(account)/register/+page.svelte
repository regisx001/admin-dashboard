<script lang="ts">
	import { pb } from '$lib';
	import { base } from '$app/paths';
	import { Button } from '@ui/button/index.js';
	import { Input } from '@ui/input/index.js';
	import { Label } from '@ui/label/index.js';
	import * as Tooltip from '$lib/components/ui/tooltip/index.js';
	import { GithubLogo } from 'svelte-radix';
</script>

<div class="h-screen w-full lg:grid lg:grid-cols-2">
	<div class="flex items-center justify-center py-12">
		<div class="mx-auto grid w-[350px] gap-6">
			<div class="grid gap-2 text-center">
				<h1 class="text-3xl font-bold">Register</h1>
				<p class="text-balance text-muted-foreground">
					Enter your email below to register new account
				</p>
			</div>
			<div class="grid gap-4">
				<div class="grid gap-2">
					<Label for="email">Email</Label>
					<Input id="email" type="email" placeholder="m@example.com" required />
				</div>

				<div class="grid gap-2">
					<div class="flex items-center">
						<Label for="password">Password</Label>
					</div>
					<Input id="password" type="password" required />
				</div>

				<div class="grid gap-2">
					<div class="flex items-center">
						<Label for="password">Password Confirm</Label>
					</div>
					<Input id="password" type="password" required />
				</div>

				<Button type="submit" class="w-full">Sign Up</Button>

				<div class="flex flex-row gap-2">
					<Tooltip.Root>
						<Tooltip.Trigger asChild let:builder>
							<Button builders={[builder]} variant="outline" class="w-full">
								<GithubLogo />
							</Button>
						</Tooltip.Trigger>
						<Tooltip.Content>
							<p>Login using Github</p>
						</Tooltip.Content>
					</Tooltip.Root>

					<Tooltip.Root>
						<Tooltip.Trigger asChild let:builder>
							<Button builders={[builder]} variant="outline" class="w-full">
								<svg
									xmlns="http://www.w3.org/2000/svg"
									width="24"
									height="24"
									viewBox="0 0 24 24"
									fill="none"
									stroke="currentColor"
									stroke-width="2"
									stroke-linecap="round"
									stroke-linejoin="round"
									class="icon icon-tabler icons-tabler-outline icon-tabler-brand-google"
									><path stroke="none" d="M0 0h24v24H0z" fill="none" /><path
										d="M20.945 11a9 9 0 1 1 -3.284 -5.997l-2.655 2.392a5.5 5.5 0 1 0 2.119 6.605h-4.125v-3h7.945z"
									/></svg
								>
							</Button>
						</Tooltip.Trigger>
						<Tooltip.Content>
							<p>Login using Google</p>
						</Tooltip.Content>
					</Tooltip.Root>
				</div>
			</div>
			<div class="mt-4 text-center text-sm">
				Already have an account!
				<a href="{base}/login" class="underline"> Sign in </a>
			</div>
		</div>
	</div>
	<div class="hidden bg-muted lg:block">
		<img
			src="{base}/login_bg.jpg"
			alt="placeholder"
			width="1920"
			height="1080"
			class="h-full w-full object-cover dark:brightness-[0.3] dark:grayscale"
		/>
	</div>
</div>
