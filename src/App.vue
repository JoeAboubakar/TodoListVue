<template>
  <div>
    <header class="bg-white shadow" v-if="$route.meta.title">
      <div class="max-w-7xl mx-auto py-6 px-4 sm:px-6 lg:px-8">
        <h1 class="text-center font-medium leading-snug text-5xl text-indigo-700">{{ $route.meta.title }}</h1>
      </div>
    </header>
    <main>
      <router-view/>
    </main>
  </div>
</template>
