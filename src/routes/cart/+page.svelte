<script>
  let email = "";
  let password = "";
  let isValid = false;
  let message = "";
  let showSuccess = false;

  const primeRegex = /\b(2|3|5|7|11|13|17|19|23|29|31|37|41|43|47|53|59|61|67|71|73|79|83|89|97)\b/;
  const rainbowColors = ["red", "orange", "yellow", "green", "blue", "indigo", "violet"];
  const gnuPhrases = [
    "GNU/Linux",
    "Linux is the kernel",
    "GNU system",
    "free software",
    "the GNU Project",
    "corelibs",
    "shell utilities",
    "kernel is an essential part"
  ];

  const conditions = [
    { label: "At least 100 characters", test: pw => pw.length >= 100 },
    { label: "Lowercase letter", test: pw => /[a-z]/.test(pw) },
    { label: "Uppercase letter", test: pw => /[A-Z]/.test(pw) },
    { label: "Number", test: pw => /\d/.test(pw) },
    { label: "Special character (!@#$%^&*)", test: pw => /[!@#$%^&*]/.test(pw) },
    { label: "Must contain 'Digga'", test: pw => /Digga/i.test(pw) },
    { label: "Contains Roman numeral 'L'", test: pw => /L/.test(pw) },
    { label: "Includes a prime number", test: pw => primeRegex.test(pw) },
    { label: "Includes a rainbow color", test: containsRainbowColor },
    { label: "Has the GNU/Linux Copypasta in it", test: containsGNUCopypasta },
  ];

  function containsRainbowColor(pw) {
    return rainbowColors.some(color => pw.toLowerCase().includes(color));
  }

  function containsGNUCopypasta(pw) {
    return gnuPhrases.some(phrase => pw.toLowerCase().includes(phrase.toLowerCase()));
  }

  $: {
    const errors = conditions.filter(c => !c.test(password));
    isValid = errors.length === 0 && email.includes("@");
    message = isValid ? "✅ Password is valid!" : "❌ Check password requirements below";
  }

  function handleLogin() {
    if (isValid) {
      showSuccess = true;
    }
  }
</script>

<div class="max-w-md mx-auto mt-16 p-6 bg-base-200 text-base-content rounded-box shadow-xl space-y-6">
  <h1 class="text-3xl font-bold text-primary">Signup</h1>
  <p class="text-sm text-base-content/60">Secure your soul. Enter your email and a mythical password. We would never sell this data.</p>

  <input
    type="email"
    bind:value={email}
    placeholder="Email"
    class="input input-bordered w-full"
  />

  <textarea
    bind:value={password}
    rows="4"
    placeholder="Enter the mythical password..."
    class="textarea textarea-bordered w-full resize-none"
  ></textarea>

  <p class={isValid ? "text-success" : "text-error"}>{message}</p>

  <ul class="text-sm space-y-1">
    {#each conditions as c}
      <li class="flex items-center">
        <span class="w-5 h-5">
          {#if c.test(password)}
            <svg xmlns="http://www.w3.org/2000/svg" class="text-success w-5 h-5" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M16.707 5.293a1 1 0 00-1.414 0L9 11.586 6.707 9.293a1 1 0 10-1.414 1.414l3 3a1 1 0 001.414 0l7-7a1 1 0 000-1.414z" clip-rule="evenodd" /></svg>
          {:else}
            <svg xmlns="http://www.w3.org/2000/svg" class="text-error w-5 h-5" viewBox="0 0 20 20" fill="currentColor"><path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zm2.83-11.17a1 1 0 00-1.41-1.41L10 8.59 8.59 7.17a1 1 0 10-1.41 1.41L8.59 10l-1.41 1.41a1 1 0 101.41 1.41L10 11.41l1.41 1.41a1 1 0 001.41-1.41L11.41 10l1.42-1.41z" clip-rule="evenodd" /></svg>
          {/if}
        </span>
        <span class="ml-2">{c.label}</span>
      </li>
    {/each}
  </ul>

  <button
    class="btn btn-primary w-full"
    disabled={!isValid}
    on:click={handleLogin}
  >
    Login
  </button>

  {#if showSuccess}
    <div role="alert" class="alert alert-success mt-4 flex items-center space-x-2">
      <svg xmlns="http://www.w3.org/2000/svg" class="w-6 h-6 shrink-0 stroke-current text-success" fill="none" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
      </svg>
      <span>Your password passed the myth-check. You're in!</span>
    </div>
  {/if}
</div>
