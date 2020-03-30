<template>
    <div>
        <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
        <app-persons v-bind:persons="persons"></app-persons>
        <ul>
          <li v-for="person in persons">{{ person.name }}</li>
        </ul>
        <app-footer v-bind:title="title"></app-footer>
    </div>
</template>

<script>
// Imports
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Persons from './components/Persons.vue';

export default {
    components: {
        'app-header': Header,
        'app-footer': Footer,
        'app-persons': Persons
    },
    data () {
        return {
          persons: [
              {name: 'Shubham', speciality: 'Vue Components', show: false},
              {name: 'Parth', speciality: 'AWS', show: false},
              {name: 'Abhi', speciality: 'JAVA', show: false},
              {name: 'Ravi', speciality: 'Angular', show: false},
              {name: 'Jay', speciality: 'React', show: false},
              {name: 'Sudip', speciality: 'Python', show: false}
          ],
          title: 'Specialist'
        }
    },
    methods: {
      updateTitle: function(updatedTitle){
        this.title = updatedTitle;
      }
    }
}
</script>

<style>
body{
    margin: 0;
    font-family: 'Nunito SemiBold';
}
</style>
