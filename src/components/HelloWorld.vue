<template>
  <div>
    <h1>Animals</h1>
    <table>
      <thead>
        <tr>
          <th>Species</th>
          <th>Name</th>
          <th>Date of birth</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(animal, key) in animals" :key="key">
          <td>{{animal.species}}</td>
          <td>{{animal.name}}</td>
          <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'Unknown' }}</td>
          <td class="text-right">
            <button class="btn btn-danger btn-sm" @click="remove(animal)">Remove</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        animals: [{
            species: 'Fish',
            name: 'Shark',
            dateOfBirth: (new Date()),
          },
          {
            species: 'Mamal',
            name: 'Lion',
            dateOfBirth: (new Date()),
          },
          {
            species: 'Mamal',
            name: 'Tiger',
            dateOfBirth: (new Date()),
          },
          {
            species: 'Fish',
            name: 'Shark',
            dateOfBirth: '',
          },
          {
            species: 'Fish',
            name: 'Catfish',
            dateOfBirth: (new Date()),
          },
          {
            species: 'Mamal',
            name: 'Elephant',
            dateOfBirth: (new Date()),
          },
          {
            species: 'Reptile',
            name: 'Snake',
            dateOfBirth: '',
          }
        ],
      };
    },
    methods: {
      remove(animal) {
        const index = this.animals.indexOf(animal);
        this.animals.splice(index, 1);
      }
    }
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
    color: #42B983;
  }
</style>