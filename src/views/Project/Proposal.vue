<template>
  <div>
    <template>
      <div class="container">
        <section class="form">
          <b-field label="Title">
              <b-input v-model="title"/>
          </b-field>

          <b-field label="募集期間">
            <b-input v-model="validDate"
              type="date"/>
          </b-field>

          <b-field label="募集金額">
              <b-input class="money" v-model="sum" type="number" step="0.0000001" placeholder="ETH" />
          </b-field>

          <b-field label="Content">
              <b-input maxlength="200" type="textarea" v-model="content"></b-input>
          </b-field>
        </section>

        <a class="button is-primary is-focused" @click="sendData">登録</a>
      </div>
    </template>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      validDate: '',
      sum: '',
      content: ''
    }
  },
  methods: {
    sendData() {
      window.registerProject(
        this.title,
        Math.floor(new Date().getTime() / 1000) + 3600,
        this.sum,
        this.content
      );
    },
  },
}
</script>

<style lang="scss" src="./css/Proposal.scss" scoped>
</style>
