<template>
  <div>
    <section style="height: 400px;" class="bg-blue-100 p-32 flex justify-center items-center"
      :style="`background-image: linear-gradient(to bottom, rgba(245, 246, 252, 0.52), rgba(117, 19, 93, 0.73)), url('${plants[currentId].photo}'); background-size: cover; background-position: center;`">
      <h1 class="text-5xl font-bold bg-clip-text text-transparent bg-gradient-to-r from-blue-600 to-purple-700">
        {{ plants[currentId].name }}
      </h1>
    </section>
    <div class="container mx-auto">
      <div>
        <h1 class="text-6xl font-extrabold text-gray-700 mb-5">¿Qué es?</h1>
        <p class="mb-3 font-light text-left text-gray-500" v-for="(is, index) in plants[currentId].what_is" :key="index">
          {{ is }}
        </p>
      </div>
      <br>
      <div>
        <h1 class="text-4xl font-extrabold text-gray-700 mb-5">Cuidado</h1>
        <div class="flex flex-col">
          <div class="overflow-x-auto sm:-mx-6 lg:-mx-8">
            <div class="inline-block min-w-full py-2 sm:px-6 lg:px-8">
              <div class="overflow-hidden">
                <table class="min-w-full text-left text-sm font-light">
                  <thead class="border-b font-medium">
                    <tr>
                      <th scope="col" class="px-6 py-4">Tipo</th>
                      <th scope="col" class="px-6 py-4">Descripcion</th>
                    </tr>
                  </thead>
                  <tbody>
                    <tr class="border-b break-words" v-for="care in plants[currentId].care" :key="care.id">
                      <td class="px-6 py-4 whitespace-nowrap font-black">
                        {{ care.type }}
                      </td>
                      <td class="px-6 py-4 break-words">
                        {{ care.detail }}
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
  </div>
</template>

<script>
import plants from '@/static/json/plants.json';

export default {
  async created() {
  },
  data() {
    return {
      plants: plants,
      currentId: (this.$nuxt.$route.params.id - 1)
    }
  },
}
</script>
