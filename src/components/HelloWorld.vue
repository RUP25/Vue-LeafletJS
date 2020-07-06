<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      IT and GeoInformatics Group is the backbone of the Centre to provide
      various operational IT and GeoInformatics related services. The group is
      responsible for establishing high technology infrastructure support to
      enable NE states to adopt space technology inputs for their development.
      Following are the major objectives of the group<br />
      check out
      <a
        href="https://nesac.gov.in/it-geo-informatics/"
        target="_blank"
        rel="noopener"
        >nesac(rs/gis divison)</a
      >.
    </p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  }
};
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
