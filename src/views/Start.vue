<template>
  <h1>Create Your Crowdfunding Campaign</h1>
  <div class="normal">
   <table style="margin: auto">
   <tr><td>Campaign Name</td>
   <td><input v-model="campaignName" type="text"></td></tr>
   <tr><td>Funding Token's Address<br/>(enter 0x2711 for BCH)</td>
   <td><input v-model="coinType" type="text" placeholder="Please enter an address in HEX format"></td></tr>
   <tr><td>Description</td>
   <td><textarea v-model="description" placeholder="Write something about your project" rows="10" cols="70"></textarea></td></tr>
   <tr><td>Deadline<br/>(no donation accepted after it)</td>
   <td><input v-model="deadline" type="datetime-local"></td></tr>
   <tr><td>Lower Bound of Funding Target</td>
   <td><input v-model="minRaisedAmount" type="text" placeholder="Please enter a number such as 8.2"></td></tr>
   <tr><td>Upper Bound of Funding Target</td>
   <td><input v-model="maxRaisedAmount" type="text" placeholder="Please enter a number such as 9.2"></td></tr>
   <tr><td>Minimum Donation from<br/>one single Donator</td>
   <td><input v-model="minDonationAmount" type="text" placeholder="Please enter a number such as 0.1"></td></tr>
   </table>
   <hr/>
   <p style="margin: auto; width: 40%"><button @click="submit" style="font-size: 24px; width: 300px">Start New Campaign</button></p>
    <p><b>NOTE:</b> to prevent resource-abusement, FlipSmarter always make you deposit --- BCH as pledge to start a campaign. When it is finished, no matter successfully or unsuccessfully, you can take back this pledge.</p>
  </div>
</template>

<style>
input {
    font-size:20px;
    width:500px;
}
textarea {
    font-size:20px;
    width:500px;
}
</style>
