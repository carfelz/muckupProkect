<template>
  <div>
    <q-btn flat>
      <q-avatar size="32px" style="height: 1em; width: 1em;">
        <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
      </q-avatar>

      <q-menu>
        <div class="row no-wrap q-pa-md">
          <div class="column items-center">
            <q-avatar size="72px">
              <img src="https://cdn.quasar.dev/img/boy-avatar.png" />
            </q-avatar>

            <div
              class="text-subtitle1 q-mt-md q-mb-xs"
              style="font-size: 12px !important;"
            >
              <b>Carlos Feliz</b>
            </div>
            <q-btn
              outline
              color="secondary"
              label="Account"
              size="md"
              class="q-ma-md"
            />

            <q-btn
              outline
              color="warning"
              label="Logout"
              size="sm"
            />
          </div>
        </div>
      </q-menu>
    </q-btn>
  </div>
</template>

<script>
  export default {
    name: 'AccountMenu',
    computed: {
      user() {
        return this.$store.state.auth.user;
      },
    },
    methods: {
      async logout() {
        this.$q.loading.show();
        await this.$store.dispatch('auth/logout').then((res) => {
          this.$q.loading.hide();
        });
      },
      getUsername() {
        if (this.user) {
          return `${this.user.firstname} ${this.user.lastname}`;
        }
      },
    },
    data() {
      return { mobileData: true, bluetooth: false, other: false };
    },
  };
</script>

<style>
  .q-btn--round {
    min-width: 0em;
    min-height: 0em;
    margin-left: 5px;
    margin-right: 20px;
  }
</style>