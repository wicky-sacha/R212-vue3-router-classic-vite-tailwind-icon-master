<template>
  <div class="relative flex items-center justify-center gap-2 rounded-lg bg-indigo-500 px-4 py-2.5">
    <p class="flex-shrink-0 flex-grow-0 text-center text-sm font-bold text-white">
      <!-- Exemple d'usage de slot pour le contenu.
    "<slot />" sera remplacé par le contenu mit entre les balise "<bouton>contenu</bouton>" de chaque instance -->
      <slot />
    </p>
  </div>
</template>