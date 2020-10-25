<template>
  <ul>
    <li v-for="restaurant in restaurants">{{restaurant.name}}</li>
  </ul>
</template>

<script lang="ts">
import {Component, Prop, Vue} from 'vue-property-decorator';
import restaurantQuery from '~/graphql/restaurants.graphql';
import {Restaurant} from "~/types/types";

@Component({
    apollo: {
      restaurants: {
        query: restaurantQuery
      }
    }
  }
)
export default class Note extends Vue {
  restaurants: Restaurant[] = [];
}
</script>
