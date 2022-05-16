<template>
  <header class="flex">
    <icon-logo />
    <FilmIcon class="h-5 w-5 fill-blue-300 stroke-blue-600" />
    <nav class="flex-auto">
      <RouterLink to="/" class="text-blue-600 underline">Accueil</RouterLink>
      <button class="texte-xl relative z-50" aria-haspopup="true" :aria-expanded="menu" @click="menuOuvert = !menuOuvert">
        <MenuIcon class="h-5 w-5" />
        <span class="sr-only">Menu</span>
      </button>
    </nav>
  </header>

  <RouterView />

  <!-- Composant /src/components/Bouton.vue 
    Exemple d'usage de slot pour le contenu -->
  <Bouton class="grid grid-cols-[repeat(auto-fit,minmax(1rem,max-content))]">Test de bouton</Bouton>

  <div class="grid grid-flow-row-dense grid-cols-[repeat(auto-fit,minmax(10rem,max-content))] gap-10 p-2">
    <!-- Les images sont simplement l'URL absolue (depuis la racine, débute par '/' )
      Pour passer une chaine de caratére *satique/litérale* : on note l'attribut de façon classique.
      Pour passer une valeur dynamique ou un nombre ou autre (booléen) : on utilise un "binding" avec ':', le contenu de l'attribut devient alors du JS qui est interpreté.
      -->
    <card :nbr-s-d-b="2" :prix="500000" image="/images-maisons/maison-1.jpg" nom="Beverly Springfield" />
    <!-- Pour un booléen il est possible de noter juste le nom de l'attribut pour le mettre à 'true' -->
    <card :nbr-s-d-b="1" :prix="2700000" favori image="/images-maisons/maison-2.jpg" nom="NY City" />
    <card :nbr-s-d-b="3" :prix="700000" image="/images-maisons/maison-1.jpg" nom="San Francisco" />
    <card :nbr-s-d-b="7" :prix="150000" :favori="true" image="/images-maisons/maison-2.jpg" nom="San Pedro" />
  </div>

  <div
    id="menu"
    class="fixed inset-0 translate-x-full bg-red-200 motion-safe:transition-transform motion-safe:duration-1000"
    :class="{ 'translate-x-0': menuOuvert }"
  >
    <ul class="hidden flex-auto justify-center gap-2 sm:flex">
      <!-- Autre menu -->
      <li><router-link to="/">Un</router-link></li>
      <li><router-link to="/">Deux</router-link></li>
      <li><router-link to="/">Trois</router-link></li>
    </ul>
  </div>
</template>

<script>
import IconLogo from "./components/icons/IconLogo.vue";
import { FilmIcon } from "@heroicons/vue/outline";
import card from "./components/card.vue";
import Bouton from "./components/Bouton.vue";
import { MenuIcon } from "@heroicons/vue/solid";
export default {
  name: "App",
  data() {
    return {
      menuOuvert: false,
    };
  },
  components: { IconLogo, FilmIcon, card, Bouton, MenuIcon },
};
</script>