<template>
  <div class="flex button-container align-center">
    <v-text-field
      class="text-field"
      placeholder="Поиск числа"
      :value="SearchedValue"
      @input="SearchedValue = $event"
      @keyup.enter="SearchValue"
    >
      <v-tooltip
        slot="append"
        max-width="300"
        bottom
      >
        <template v-slot:activator="{ on }">
          <v-icon
            class="h-8"
            color="primary"
            dark
            v-on="on"
          >
            mdi-help-circle
          </v-icon>
        </template>
      </v-tooltip>
    </v-text-field>
    <v-btn
      class="button"
      color="primary"
      :disabled="disabled"
      dark
      @click="SearchValue"
    >
      Поиск
    </v-btn>
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
  props: {
    disabled: { type: Boolean },
  },
  data() {
    return {
      SearchedValue: '',
    };
  },
  methods: {
    SearchValue() {
      if (this.SearchedValue !== '' && !this.disabled) {
        console.log(this.SearchedValue);
        this.$emit('myEvent', this.SearchedValue);
        this.SearchedValue = '';
      }
    },
  },
};
</script>

<style>
.button-container {
  width: 100%;
  max-width: 300px;
}
.text-field{
  margin-right: 1rem;
}
.button {
  min-width: fit-content !important;
}
</style>
