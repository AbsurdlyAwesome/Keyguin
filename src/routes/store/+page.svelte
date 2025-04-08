<script>
  import { goto } from '$app/navigation';

  function goToCart(distro) {
    // Optional: Pass distro name or details as query parameters
    const name = encodeURIComponent(distro.name);
    goto(`/cart?distro=${name}`);
  }

  const distros = [
    {
      name: "Arch Linux",
      price: "$9/mo",
      badge: { text: "Minimalist", style: "info" },
      features: [
        "Free Acces to our Community Forum",
        "Feels elite",
        { text: "GUI", disabled: true }
      ],
      button: "Install Pain"
    },
    {
      name: "Gentoo",
      price: "$19/mo",
      badge: { text: "For Pros", style: "accent" },
      features: [
        "Free one Time Therapist Pass",
        'Free wallpaper',
        { text: "Time Efficiency", disabled: true }
      ],
      button: "Recompile My Life"
    },
    {
      name: "Fedora",
      price: "$19/mo",
      badge: { text: "Elegant", style: "warning" },
      features: [
        "Free Sticker",
        'Custom Keyguin Kernel',
        { text: "Option to change Wallpaper", disabled: true }
      ],
      button: "Compile My Life"
    },
    {
      name: "Hannah Montana Linux",
      price: "$19/mo",
      badge: { text: "Limited Edition", style: "secondary" },
      features: [
        "Best of All Worlds",
        "Great Gift For Your Girlfriend",
        { text: "Will not be Having a girlfriend after this", disabled: true }
      ],
      button: "Yassify My Shell"
    },
    {
      name: "Red Star OS",
      price: "$99/mo",
      badge: { text: "State Approved", style: "error" },
      features: [
        "Preinstalled Spyware!",
        "Comes pre-firewalled",
        { text: "Freedom (who needs that anyway)", disabled: true }
      ],
      button: "Join the OS Revolution"
    }
  ];
</script>

<div class="container mx-auto p-8 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-8">
  {#each distros as distro}
    <div class="card w-full bg-base-100 shadow-sm">
      <div class="card-body">
        <span class="badge badge-xs badge-{distro.badge.style}">
          {distro.badge.text}
        </span>

        <div class="flex justify-between mt-2">
          <h2 class="text-3xl font-bold">{distro.name}</h2>
          <span class="text-xl">{distro.price}</span>
        </div>

        <ul class="mt-6 flex flex-col gap-2 text-xs">
          {#each distro.features as feature}
            <li class={feature.disabled ? "opacity-50" : ""}>
              <svg class={`size-4 me-2 inline-block ${feature.disabled ? "text-base-content/50" : "text-success"}`} fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
              </svg>
              <span class={feature.disabled ? "line-through" : ""}>
                {typeof feature === "string" ? feature : feature.text}
              </span>
            </li>
          {/each}
        </ul>

        <div class="mt-6">
          <button class="btn btn-primary btn-block" on:click={() => goToCart(distro)}>
            {distro.button}
          </button>
        </div>
      </div>
    </div>
  {/each}
</div>
