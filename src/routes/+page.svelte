<script>
  import { goto } from '$app/navigation';

  function goToStore() {
    goto('/store');
  }
</script>


<div class="hero bg-base-200 min-h-screen">
  <div class="hero-content flex-col lg:flex-row">
    <img src="/activate.png" class="max-w-sm rounded-lg shadow-2xl" alt="Activate Screenshot" />
    <div>
      <h1 class="text-5xl font-bold">Is that watermark bothering you?</h1>
      <p class="py-6">
        Linux is the superior operating system — but $300 just to remove a watermark?
        That’s a hard no.
      </p>
      <h2 class="text-2xl font-semibold mb-4">
        At <strong>Keyguin</strong>, we offer Great Linux Key Subsriptions.
      </h2>
      <p class="text-base italic mb-6">
        Cheaper than a Door license, and more reliable than your last situationship.
      </p>
<button class="btn btn-primary" on:click={goToStore}>Browse Our Catalog</button>
    </div>
  </div>
</div>

<div class="px-8 py-12 bg-base-100">
  <h2 class="text-4xl font-bold text-center mb-8">What Our Users Are Saying</h2>
  <div class="grid gap-6 grid-cols-1 sm:grid-cols-2 lg:grid-cols-3">
    <div class="card bg-base-200 shadow-md p-6">
      <div class="flex items-center gap-4 mb-2">
        <img class="w-12 h-12 rounded-full" src="" alt="P" />
        <div>
          <p class="font-semibold">Peter M.</p>
          <div class="rating">
            {#each Array(5) as _}
              <div class="mask mask-star bg-yellow-400"></div>
            {/each}
          </div>
        </div>
      </div>
      <p>Was skeptical, but this actually worked. Now I'm Superior. 10/10 would sudo again.</p>
    </div>

    <div class="card bg-base-200 shadow-md p-6">
      <div class="flex items-center gap-4 mb-2">
        <img class="w-12 h-12 rounded-full" src="" alt="M" />
        <div>
          <p class="font-semibold">Michael Mortindon</p>
          <div class="rating">
            {#each Array(5) as _}
              <div class="mask mask-star bg-yellow-400"></div>
            {/each}
          </div>
        </div>
      </div>
      <p>I thought it was a scam, but the Fedora key slapped. Even came with a free sticker!</p>
    </div>

    <div class="card bg-base-200 shadow-md p-6">
      <div class="flex items-center gap-4 mb-2">
        <img class="w-12 h-12 rounded-full" src="" alt="B" />
        <div>
          <p class="font-semibold">B. Fences</p>
          <div class="rating">
            {#each Array(5) as _}
              <div class="mask mask-star bg-yellow-400"></div>
            {/each}
          </div>
        </div>
      </div>
      <p>Honestly better support than real OEM keys. My Ubuntu install activated itself while I did nothing.</p>
    </div>
  </div>
</div>

<ul class="timeline timeline-vertical p-8">
  <li>
    <div class="timeline-start timeline-box">Keyguin gets domain name</div>
    <div class="timeline-middle">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="text-primary h-5 w-5" viewBox="0 0 20 20">
        <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm4-10l-4 5-2-2-1 1 3 3 5-6z" />
      </svg>
    </div>
    <hr class="bg-primary" />
  </li>
  <li>
    <hr class="bg-primary" />
    <div class="timeline-middle">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="text-primary h-5 w-5" viewBox="0 0 20 20">
        <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm4-10l-4 5-2-2-1 1 3 3 5-6z" />
      </svg>
    </div>
    <div class="timeline-end timeline-box">Native Activator Released</div>
    <hr class="bg-primary" />
  </li>
  <li>
    <hr class="bg-primary" />
    <div class="timeline-start timeline-box">First 1,000 Users</div>
    <div class="timeline-middle">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="text-primary h-5 w-5" viewBox="0 0 20 20">
        <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm4-10l-4 5-2-2-1 1 3 3 5-6z" />
      </svg>
    </div>
    <hr />
  </li>
  <li>
    <hr />
    <div class="timeline-middle">
      <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="h-5 w-5" viewBox="0 0 20 20">
        <path d="M10 18a8 8 0 100-16 8 8 0 000 16zm4-10l-4 5-2-2-1 1 3 3 5-6z" />
      </svg>
    </div>
    <div class="timeline-end timeline-box">Community Meme Contest</div>
    <hr />
  </li>
</ul>

