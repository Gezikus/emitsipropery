<template>
  <div class="hello">
    <section class="moreInfoAboutClient">
      <h2>Dane klienta</h2>
      <div class="aboutClient">
        <p>
          Imię: <span>{{ client.name }}</span>
        </p>
        <p>
          Nazwisko:
          <span>{{ client.surname }}</span>
        </p>
        <p>
          Nazwa firmy:
          <span>{{ client.companyName }}</span>
        </p>
        <p>
          NIP: <span>{{ client.nip }}</span>
        </p>
        <p>
          Adres: <span>{{ client.address }}</span>
        </p>
        <p>
          Pesel: <span>{{ client.pesel }}</span>
        </p>
        <p>
          Telefon: <span>{{ client.phoneNumber }}</span>
        </p>
        <p>
          E-mail: <span>{{ client.email }}</span>
        </p>
      </div>
      <v-btn @click="returnClient(clientt)">
        To ja Patryk
      </v-btn>
    </section>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  emits: ["returnClient"],
  data: () => {
    return {
      clientt: { imie: "Patryk", nazwisko: "Gerczuk" },
    };
  },
  props: {
    client: Object,
  },
  methods: {
    returnClient(object) {
      this.$emit("returnClient", object);
    },
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
