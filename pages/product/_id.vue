<template>
  <div>
    Location : {{ this.$route.params.id.data[0].location }} <br><br>
    Date_created : {{ this.$route.params.id.data[0].date_created }} <br><br>
    Title : {{ this.$route.params.id.data[0].title }} <br><br>
    Keyword : {{ this.$route.params.id.data[0].keywords }} <br><br>
    Picture :{{ this.$route.params.id.links[0].href }} <br><br>
    Description_508 : {{ this.$route.params.id.data[0].description_508 }} <br><br>
    Description : {{ this.$route.params.id.data[0].description }} <br><br>
  </div>
</template>
