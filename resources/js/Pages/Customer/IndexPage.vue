<script setup>
import {Inertia} from "@inertiajs/inertia";

defineProps({
  customers: Array
})

const deleteItem = (id)=>{
  Inertia.delete(route('customer.destroy', id));
}
</script>

<template>
  Müşteri listesi <br>
  <ul>

    <template v-for="customer in customers">
      <li>
        <div class="flex space-x-6">
          <span>{{customer.name}}</span>
          <span class="text-rose-500" @click="deleteItem(customer.id)">Sil</span>
        </div>
      </li>
    </template>
  </ul>
</template>