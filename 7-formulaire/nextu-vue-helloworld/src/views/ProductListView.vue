<script lang="ts" setup>
import type { Product } from '@/models/product'
const props = defineProps<{
  products: Product[]
}>()
</script>
<template>
  <div>
    <table>
      <tr>
        <th>id</th>
        <th>label</th>
        <th>description</th>
        <th>statut</th>
      </tr>
      <tbody>
        <tr v-for="(product, i) in props.products" :key="i">
          <td>{{ product.id }}</td>
          <td>{{ product.label }}</td>
          <td>{{ product.description }}</td>
          <td>
            <div v-if="product.qte > 0">disponible</div>
            <div v-else>indisponible</div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
