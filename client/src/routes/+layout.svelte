<script lang="ts">
	import '../app.css';
	import 'flowbite';
	let { children } = $props();
	import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
	import { Footer, FooterCopyright, FooterLinkGroup, FooterLink } from 'flowbite-svelte';
	import { Breadcrumb, BreadcrumbItem } from 'flowbite-svelte';

	import { page } from '$app/stores';
	import { derived } from 'svelte/store';

	const activeUrl = derived(page, $page => $page.url.pathname);
</script>

<header>
	<Navbar>
		<NavBrand href="/">
			<img src="/images/flowbite-svelte-icon-logo.svg" class="me-3 h-6 sm:h-9" alt="Flowbite Logo" />
			<span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Flowbite</span>
		</NavBrand>
		<NavHamburger />
		<NavUl {activeUrl}>
			<NavLi href="/">Home</NavLi>
			<NavLi href="/navbar">Navbar</NavLi>
			<NavLi href="/accordion">Accordion</NavLi>
			<NavLi href="/alert">Alert</NavLi>
			<NavLi href="/avatar">Avatar</NavLi>
		</NavUl>
	</Navbar>
</header>

<Breadcrumb aria-label="Default breadcrumb example">
	<BreadcrumbItem href="/" home>Home</BreadcrumbItem>
	<BreadcrumbItem href="/">Projects</BreadcrumbItem>
	<BreadcrumbItem>Flowbite Svelte</BreadcrumbItem>
  </Breadcrumb>

<main>
	{@render children()}
</main>

<Footer>
	<div class="sm:flex sm:items-center sm:justify-between">
		<FooterCopyright href="/" by="Flowbite™" year={2022} />
		<FooterLinkGroup ulClass="flex flex-wrap items-center mt-3 text-sm text-gray-500 dark:text-gray-400 sm:mt-0">
			<FooterLink href="/">About</FooterLink>
			<FooterLink href="/">Privacy Policy</FooterLink>
			<FooterLink href="/">Licensing</FooterLink>
			<FooterLink href="/">Contact</FooterLink>
		</FooterLinkGroup>
	</div>
</Footer>
