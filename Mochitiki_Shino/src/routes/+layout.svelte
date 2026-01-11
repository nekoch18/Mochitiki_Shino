<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import '$lib/css/style.css';
	import { page } from '$app/stores';

	let { children } = $props();

	let title = $derived(getTitle($page.url.pathname));

	function getTitle(pathname: string) {
		switch (pathname) {
			case '/':
				return 'Mochitiki Shino';
			case '/about':
				return 'About | Mochitiki Shino';
			case '/earthquakeinformation':
				return '地震情報について | Mochitiki Shino';
			case '/terms':
				return '利用規約 | Mochitiki Shino';
			case '/privacy':
				return 'プライバシーポリシー | Mochitiki Shino';
			default:
				return 'Mochitiki Shino';
		}
	}
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
	<title>{title}</title>
	<style>
    /* 背景のドットグリッド */
    body {
      background: 
        radial-gradient(circle, rgba(255,255,255,0.4) 2px, transparent 2px),
        repeating-linear-gradient(#d7d7d7 0 1px, transparent 1px 40px),
        repeating-linear-gradient(90deg, #d7d7d7 0 1px, transparent 1px 40px);
      background-size: 20px 20px, 40px 40px, 40px 40px;
      background-position: 0 0;
    }
	#hamburger9-input {
		display: none;
	}
	.hamburger9 {
		display: flex;
		width: 50px;
		/* 右上に固定表示 */
		position: fixed;
		top: 1rem;
		right: 1rem;
		z-index: 9999;
	}
	.hamburger9 div {
		position: relative;
		width: 30px;
		height: 30px;
		cursor: pointer;
	}
	.hamburger9 .line {
		position: absolute;
		display: block;
		width: 30px;
		height: 3px;
		border-radius: 5px;
		background-color: black;
		transition: all 0.6s cubic-bezier(0.68, -0.55, 0.265, 1.55);
	}
	.hamburger9 .line1 {
		top: 0;
	}
	.hamburger9 .line2,
	.hamburger9 .line3 {
		top: 13.5px;
	}
	.hamburger9 .line4 {
		bottom: 0;
	}
	.hamburger9 input:checked + label > .hamburger9-container > .line1 {
		transform: translateX(40px) scale(0);
	}
	.hamburger9 input:checked + label > .hamburger9-container > .line2 {
		transform: rotate(45deg) scale(1.2);
	}
	.hamburger9 input:checked + label > .hamburger9-container > .line3 {
		transform: rotate(-45deg) scale(1.2);
	}
	.hamburger9 input:checked + label > .hamburger9-container > .line4 {
		transform: translateX(-40px) scale(0);
	}

	/* メニュー（チェックで表示） */
	.hamburger9-menu {
		position: fixed;
		top: 3.2rem;
		right: 1rem;
		background: white;
		border-radius: 8px;
		box-shadow: 0 6px 18px rgba(0,0,0,0.12);
		padding: 0.5rem 0.75rem;
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
		opacity: 0;
		transform: translateY(-6px) scale(0.98);
		transition: opacity 180ms ease, transform 180ms ease;
		pointer-events: none;
		min-width: 160px;
	}

	.hamburger9-menu .menu-item {
		display: block;
		padding: 0.5rem 0.75rem;
		color: #111827;
		text-decoration: none;
		border-radius: 6px;
		font-weight: 600;
	}

	.hamburger9-menu .menu-item:hover {
		background: rgba(0,0,0,0.06);
	}

	/* チェック時に表示 */
	.hamburger9 input:checked + label + .hamburger9-menu {
		opacity: 1;
		transform: translateY(0) scale(1);
		pointer-events: auto;
	}

	/* full-bleed: 親が中央寄せでも表示をビューポート幅いっぱいにする */
	.full-bleed {
		width: 100vw;
		position: relative;
		left: 50%;
		right: 50%;
		margin-left: -50vw;
		margin-right: -50vw;
	}
	</style>
</svelte:head>

<main style="padding-bottom: 5rem;">
	{@render children()}
</main>
