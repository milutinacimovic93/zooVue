<template>
  <div>
    <h1>Animals</h1>
    <form @submit.prevent="addNewAnimal">
        <label for="species">Species:</label>
        <input class="form-control" name="species" type="text" v-model="newAnimal.species"/>
        <label for="name">Name:</label>
        <input class="form-control" name="name" type="text" v-model="newAnimal.name"/>
        <label for="dateOfBirth">Date of birth:</label>
        <input class="form-control" name="dateOfBirth" type="text" v-model="newAnimal.dateOfBirth"/>
        <button class="submit">Add Animal</button>
    </form>
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
            <button class="btn btn-danger btn-sm" @click="moveToTop(animal)">Move to top</button>
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
        newAnimal: {

       }
      };
    },
    methods: {
      remove(animal) {
        const index = this.animals.indexOf(animal);
        this.animals.splice(index, 1);
      },

      moveToTop(animal) {
        this.remove.animal;
        this.animals.unshift(animal);
      },

      addNewAnimal() {
        this.animals.push(this.newAnimal)
        this.newAnimal = {};
      },
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