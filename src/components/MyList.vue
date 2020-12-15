<template>
<div class="container">
  <div class="mt-5 row justify-content-center">
    <div class="col-5">
      <table class="table table-hover table-dark">
        <thead>
          <tr>
            <!-- Iterate over the available inputs(options) -->
            <th scope="col" v-for="(input, index) in inputs" :key="index">
              <input type="checkbox" :value="input.value" v-model="selected" class="big-checkbox mr-2">
              <font-awesome-icon :icon="input.icon" class="fa-icon-style" />
            </th>
          </tr>
        </thead>
        <tbody>
          <!-- Iterate over the filtered list based on checkboxes -->
          <tr v-for="(item, index) in filteredList" :key="index">
            <th scope="row"><font-awesome-icon :icon="item.icon" class="fa-icon-style" v-bind:style="{ color: item.color}" /></th>
            <td>{{item.value}}</td>
            <td><input type="number" :value="item.howMany" disabled class="bg-dark text-white" style="max-width: 100px; padding-left:4px"></td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'MyList',
  data() {
    return {
      selected: ['asterisk'],
      inputs: [
        {value: 'asterisk', icon: 'asterisk'},
        {value: 'child', icon: 'child'},
        {value: 'cube', icon: 'cube'}
      ],
      list: [
        {icon: 'asterisk', value: 'asterisk', howMany: 14, color: '#8719E0'},
        {icon: 'asterisk', value: 'asterisk', howMany: 18, color: '#E9B949'},
        {icon: 'asterisk', value: 'asterisk', howMany: 28, color: '#27AB83'},
        {icon: 'child', value: 'child', howMany: 20, color: '#E9B949'},
        {icon: 'child', value: 'child', howMany: 30, color: '#8719E0'},
        {icon: 'child', value: 'child', howMany: 40, color: '#27AB83'},
        {icon: 'cube', value: 'cube', howMany: 25, color: '#E9B949'},
        {icon: 'cube', value: 'cube', howMany: 35, color: '#8719E0'},
      ]
    }
  },
  computed: {
    filteredList() {
      // Filter the list whenever the checkboxes value changes
      return this.list.filter(item => {
        return this.selected.includes(item.value)
      })
    }
  }
}
</script>

<style scoped>
  input {cursor: pointer}
  .big-checkbox {width: 16px; height: 16px;}
  .fa-icon-style {margin: 2px; font-size: 18px;}
</style>
