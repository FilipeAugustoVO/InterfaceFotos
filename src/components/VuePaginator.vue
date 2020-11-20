new Vue({
  el: '#app',
  data () {
    return {
      // The resource variable
      animals: [],
      // Here you define the url of your paginated API
      resource_url: 'https://jsonplaceholder.typicode.com/photos'
    }
  },
  components: {
    VPaginator: VuePaginator
  },
  methods: {
    updateResource(data){
      this.animals = data
    }
  }
  ...
});