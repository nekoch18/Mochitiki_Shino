<script>
    import Shino from '$lib/assets/6904231-1.webp';
</script>

<header>
    <div class="hamburger9">
        <input type="checkbox" id="hamburger9-input" />
        <label for="hamburger9-input">
          <div class="hamburger9-container">
            <span class="line line1"></span>
            <span class="line line2"></span>
            <span class="line line3"></span>
            <span class="line line4"></span>
          </div>
        </label>
      <nav class="hamburger9-menu" aria-labelledby="hamburger9-input">
        <a href="/" class="menu-item">Home</a>
        <a href="/about" class="menu-item">About</a>
        <a href="/earthquakeinformation" class="menu-item">地震情報について</a>
        <hr>
        <a href="/terms" class="menu-item">利用規約</a>
        <a href="/privacy" class="menu-item">プライバシーポリシー</a>
      </nav>
    </div>
</header>
<h1 class="text-3xl tracking-[0.2em] font-bold mb-12">Mochitiki Shino.</h1>
<div class="relative w-screen left-1/2 -translate-x-1/2 overflow-visible">
    <svg class="w-screen max-w-none" viewBox="0 0 800 120">
        <path d="M0 60 H150 L170 40 L190 80 L210 20 L230 60 H370 L390 40 L410 80 L430 20 L450 60 H800" stroke="black" stroke-width="4" fill="none" />
    </svg>
    <img src={Shino} class="absolute left-1/2 -translate-x-1/2 -top-16 w-64 select-none pointer-events-none">
</div>
