<template>
  <h1>FlipSmarter: Crowdfunding on smartBCH</h1>
  <div class="normal">
    <p>FlipSmarter is an utility for crowdfunding on smartBCH, supporting SEP20 tokens and BCH. It is inspired by <a href="https://flipstarter.cash">FlipStarter</a> and has a few enhancements.</p>
    <p>FlipSmarter is a <a href="https://www.puredapp.org">Pure DApp</a>, which means its contract code and front-end code are both opensource and anyone can deploy them at anywhere.</p>
    With FlipSmarter, you can:<br/>
    <ol>
    <li><a @click="start" href="">Start</a> a new crowdfunding campaign</li>
    <li><a @click="list" href="">List</a> recent campaigns</li>
    <li><a @click="detail" href="">View the details</a> of a campaign and donate to it</li>
    </ol>
    <p>Please read on to learn how to use it.</p>
  <h3>User Guide</h3>
    <p>Crowdfunding is the practice of funding a project by raising small amounts of coins from a large number of donators. Usually the project owner would promise some deliverables (source code, article, video, websites, tokens, etc) as feedback to the donators. FlipSmarter only takes care of the funding part and cannot enforce the deliverables.</p>
    <p>Using FlipSmarter is quite straightforward: you describe your project which the supporters donate coins to, and when the donated fund reaches a predefined funding target, the crowdfunding succeeds and you can get the fund. Each campaign has a deadline. If donated fund cannot reach the predefined funding target before this deadline, the crowdfunding fails and every donator will get back her donated coins.</p>
    <p>You can donate to a project or revoke your donation anytime before the campaign finalized. If current time reaches its deadline, or the donated fund reaches the predefined funding target, a campaign is finalized. If a campaign is finalized as a successful one, you can no longer revoke your donation.</p>
    <p>Instead of one single value, the project owner can specify two values for the funding target: the soft target and the hard target. After the deadline, if the donated fund is no less than the soft target, the campaign succeeds. Before the deadline, if the donated fund reaches the soft target, the campaign does not finalize immediately, instead, it only gets finalized at the hard target.</p>
    <p>A campaign is uniquely identified by its name, whose length must be no more than 32 bytes. We suggest to use UTF-8 string for campaign names. Only after a campaign ends its life cycle, another campaign can re-use its name.</p>
    <p>To prevent spam campaigns abuse smartBCH's on-chain resource, FlipSmarter requires the project owner to deposit a small pledge of BCH, which can be all withdrawn after the campaign ends its life cycle.</p>
    <p>A campaign ends its life cycle after all the records it created on-chain are erased. For a failed campaign, all the donators' funds must be returned. Anyone can send transactions to return the funds. And no matter a campaign is successful or failed, all its donation records must be erased, because these records take on-chain storage. Again, anyone can send transactions to erase these records.</p>
  </div>
</template>

<script>
export default {
  name: 'Home',
  methods: {
    create() {
      this.$router.push('create');
    },
    list() {
      this.$router.push('list');
    },
    detail() {
      this.$router.push('detail');
    }
  }
}
</script>
