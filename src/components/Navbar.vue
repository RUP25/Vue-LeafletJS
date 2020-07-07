<template>
  <div class="topnav" style="top :0; position: fixed; width: 100%; ">
    <b-navbar toggleable="lg" type="dark" variant="success">
      <b-container>
        <b-navbar-brand href="http://nesac.gov.in"
          ><img
            src="https://www.google.com/url?sa=i&url=https%3A%2F%2Frecruitment.nesdr.gov.in%2Fta_2019%2F&psig=AOvVaw0c19tE26LvJyOSjTyuC1XK&ust=1594190478051000&source=images&cd=vfe&ved=0CAIQjRxqFwoTCJjil7LEuuoCFQAAAAAdAAAAABAJ"
            class="d-inline-block align-top"
          />NESAC</b-navbar-brand
        >
        <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
        <b-collapse id="nav-collapse" is-nav>
          <!-- Right aligned nav items -->
          <b-navbar-nav class="ml-auto">
            <b-nav-form>
              <b-form-input
                size="sm"
                class="mr-sm-2"
                placeholder="Search for a location"
                v-model="meal"
              ></b-form-input>
              <b-button
                size="sm"
                class="my-2 my-sm-0"
                type="submit"
                @click.prevent="getMeal"
                >Search</b-button
              >
            </b-nav-form>
            <b-nav-item-dropdown right style="overflow: visible;">
              <!-- Using 'button-content' slot -->
              <template slot="button-content"><em>User</em></template>
              <b-dropdown-item href="#">Profile</b-dropdown-item>
              <b-dropdown-item href="#">Sign Out</b-dropdown-item>
            </b-nav-item-dropdown>
          </b-navbar-nav>
        </b-collapse>
      </b-container>
    </b-navbar>
  </div>
</template>
<script>
export default {
  name: "Navbar"
};
</script>
