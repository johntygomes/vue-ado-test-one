<template>
  <v-container>
    <v-row>
      <v-col>HelloWorld 1</v-col>
      <v-col>HelloWorld 2</v-col>
    </v-row>
    <v-row>
      <v-col>HelloWorld 3</v-col>
      <v-col>HelloWorld 4</v-col>
    </v-row>
    <v-row
      ><v-col>
        <v-autocomplete
          :items="items"
          outlined
          label="Outlined"
        ></v-autocomplete> </v-col
    ></v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data() {
    return {
      items: ["foo", "bar", "fizz", "buzz"],
      values: ["foo", "bar"],
      value: null,
    };
  },
  methods: {
    customFilter(item, queryText) {
      const textOne = item.name.toLowerCase();
      const textTwo = item.abbr.toLowerCase();
      const searchText = queryText.toLowerCase();

      return (
        textOne.indexOf(searchText) > -1 || textTwo.indexOf(searchText) > -1
      );
    },
  },
};
</script>
