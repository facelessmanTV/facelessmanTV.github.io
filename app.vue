var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!',
    rankings: null
  },
  created: function () {
    fetch("https://spreadsheets.google.com/feeds/list/1D8j4r-b0D1HI0GYlOlA8USnNhxF4LKUEjvrsHqRNxBg/od6/public/values?alt=json")
      .then(response => response.json())
      .then(json => {
        this.rankings=json.feed.entry;
        console.log(this.rankings);
      });
  }
})