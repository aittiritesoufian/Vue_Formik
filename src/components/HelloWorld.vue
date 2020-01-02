<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      For a guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-eslint" target="_blank" rel="noopener">eslint</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
    <section>
      <Formik @onSubmit="handleSubmit" :fields="fields">
          <Fields
              v-for="field in fields"
              v-bind:key="field.id"
              :field="field"></Fields>
      </Formik>
    </section>
  </div>
</template>

<script>
import Formik from './Formik';
import Fields from './Fields';

export default {
  name: 'HelloWorld',
  components: {
    Formik,
    Fields
  },
  data: () => ({
    fields: [
      {
          type: "text",
          name: "name",
          id: "name",
          label: "Name",
          placeholder: "Name",
          disable: false,
          value:"plop"
      },
      {
          type: "text",
          name: "description",
          id: "description",
          label: "Description",
          placeholder: "Description",
          disable: false,
          value:"desc"
      },
      {
          type: "number",
          name: "velocity",
          id: "velocity",
          label: "Vélocité",
          placeholder: "Vélocité",
          disable: false,
          value:"desc"
      },
      /*{
          type: "select",
          id: "choice",
          name: "choice",
          label: "Faites un choix",
          placeholder: "Faites un choix",
          disable: false,
          value: "choice2",
          options: [
              {
                  value: "choice1",
                  label: "Premier Choix !"
              },
              {
                  value: "choice2",
                  label: "Second Choix !"
              }
          ]
      },
      {
          type: "checkbox",
          id: "consent",
          name: "consent",
          placeholder: "Vous consentez à ceci",
          disable: false,
          value: 0
      },
      {
          type: "checkbox",
          id: "consent2",
          name: "consent2",
          label: "Vous consentez à cela",
          disable: false,
          value: 1
      },*/
      {
          type: "radio",
          id: "status",
          name: "status",
          label: "Statut",
          placeholder: "Statut",
          disable: false,
          value: "done",
          options: [
              {
                  value: "text",
                  label: "Text"
              },
              {
                  value: "done",
                  label: "Done"
              }
          ]
      }
    ]
  }),
  props: {
    msg: String
  },
  methods: {
    handleSubmit: function(e){
      console.log(e);
      // here emit an event with the getted data from form.
      //this.$emit('event', { e });
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
