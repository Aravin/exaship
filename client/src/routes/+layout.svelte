<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<header>
    <h1>My Application Header</h1>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
            <li><a href="/contact">Contact</a></li>
        </ul>
    </nav>
</header>

<main>
    {@render children()}
</main>

<footer>
    <p>© 2023 My Application. All rights reserved.</p>
</footer>
