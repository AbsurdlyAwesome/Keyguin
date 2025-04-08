<script>
  import "../style.css";
  let modal;

  function openModal() {
    modal.showModal();
  }
</script>

<!-- Navbar -->
<div class="navbar bg-base-100 shadow-sm">
  <div class="flex-1">
    <a class="btn btn-ghost text-xl font-bold">Keyguin</a>
  </div>
  <div class="flex-none flex gap-4 items-center">
    <!-- Cart Dropdown -->
    <div class="dropdown dropdown-end">
      <div tabindex="0" role="button" class="btn btn-ghost btn-circle">
        <div class="indicator">
          <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
          </svg>
        </div>
      </div>
      <div class="card card-compact dropdown-content bg-base-100 z-10 mt-3 w-52 shadow">
        <div class="card-body">
          <span class="text-lg font-bold">0 Items</span>
          <span class="text-info">Subtotal: 0</span>
          <div class="card-actions">
            <button class="btn btn-primary btn-block">View Cart</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal Trigger -->
    <button class="btn btn-outline" on:click={openModal}>Themes</button>
    <dialog bind:this={modal} class="modal">
      <div class="modal-box">
        <h3 class="text-lg font-bold">Hello!</h3>
        <div role="alert" class="alert alert-error">
  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 shrink-0 stroke-current" fill="none" viewBox="0 0 24 24">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2m7-2a9 9 0 11-18 0 9 9 0 0118 0z" />
  </svg>
  <span>Please Buy A Key In order to use Themes.</span>
</div>
        <div class="modal-action">
          <form method="dialog">
            <button class="btn">Close</button>
          </form>
        </div>
      </div>
    </dialog>

    <!-- Profile Dropdown -->
    <div class="dropdown dropdown-end">
      <div tabindex="0" role="button" class="btn btn-ghost btn-circle avatar">
        <div class="w-10 rounded-full">
          <img alt="User Avatar" src="User" />
        </div>
      </div>
      <ul tabindex="0" class="menu menu-sm dropdown-content bg-base-100 rounded-box z-10 mt-3 w-52 p-2 shadow">
        <li><a class="justify-between">Profile <span class="badge">New</span></a></li>
        <li><a>Settings</a></li>
        <li><a>Login</a></li>
      </ul>
    </div>
  </div>
</div>

<!-- Hero Section -->
<div class="hero bg-base-200 min-h-screen">
  <div class="hero-content flex-col lg:flex-row">

<!-- Footer -->
<footer class="footer sm:footer-horizontal bg-neutral text-neutral-content p-10">
  <aside>
    <svg width="50" height="50" viewBox="0 0 24 24" fill="currentColor" class="fill-current">
      <circle cx="12" cy="12" r="10" />
    </svg>
    <p>
      Keyguin Inc.<br />
      Open Source Liberation since 2024
    </p>
    <p class="text-xs mt-2">Disclaimer: Keyguin is a parody store. All keys are fictional and for entertainment use only. This is for educational purposes only.</p>
  </aside>
  <nav>

  </nav>
</footer>
