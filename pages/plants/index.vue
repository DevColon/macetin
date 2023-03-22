<template>
  <div>
    <h1>Hola</h1>
    <div class="container mx-auto">
      <div class="flex flex-col">
        <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
          <div class="inline-block min-w-full py-2 sm:px-6 lg:px-8">
            <div class="overflow-hidden">
              <table class="min-w-full text-left text-sm font-light">
                <thead class="border-b font-medium">
                  <tr>
                    <th scope="col" class="px-6 py-4">#</th>
                    <th scope="col" class="px-6 py-4">Nombre</th>
                    <th scope="col" class="px-6 py-4">Accion</th>
                  </tr>
                </thead>
                <tbody>
                  <tr class="border-b" v-for="plant in plants" :key="plant.id">
                    <td class="whitespace-nowrap px-6 py-4 font-medium">{{ plant.id }}</td>
                    <td class="whitespace-nowrap px-6 py-4">{{ plant.name }}</td>
                    <td class="whitespace-nowrap px-6 py-4">
                      <nuxt-link :to="`plants/${plant.id}`"
                        class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800">
                        Ver mas
                      </nuxt-link>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import plants from '@/static/json/plants.json';

export default {
  async created() {
  },
  data() {
    return {
      plants: plants
    }
  },
}
</script>
