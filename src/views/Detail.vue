<template>
  <h1>Campaign Details</h1>
  <div class="normal">
   <p>Campaign Name <input v-model="name" type="text"><button @click="show">Show Details</button></p>
   <hr/>
   <table style="margin: auto">
   <tr><td>Campaign Name</td>
   <td>---</td></tr>
   <tr><td>Funding Token</td>
   <td>0x-- and --- </td></tr>
   <tr><td>Fund Receiver</td>
   <td>0x-- and --- </td></tr>
   <tr><td>Description</td>
   <td><textarea rows="10" cols="70" readonly>---@-</textarea></td></tr>
   <tr><td>Deadline<br/>(no donation accepted after it)</td>
   <td>----</td></tr>
   <tr><td>Finalized?</td>
   <td>--yesno--</td></tr>
   <tr><td>Succeeded?</td>
   <td>--yesno--</td></tr>
   <tr><td>Donated Amount</td>
   <td>---</td></tr>
   <tr><td>Lower Bound of Funding Target</td>
   <td>---</td></tr>
   <tr><td>Upper Bound of Funding Target</td>
   <td>---</td></tr>
   <tr><td>Minimum Donation from<br/>one single Donator</td>
   <td>---</td></tr>
   </table>
   <hr/>
   You has never donated in this campaign. You can donate<br/>
   <input v-model="donateAmt" type="text" placeholder="Please enter the donated amount"><button @click="donate">Donate</button><br/>
   <hr/>
   This campaign has failed and you donated in this campaign. You can get back your donation.
   <button @click="getback">Get Back</button><br/>
   <hr/>
   This campaign is in progress and you have already donated in this campaign. You can revoke your donation and get back the coins:
   <button @click="undonate">Undonate</button><br/>
   <hr/>
   This campaign is in progress and you have never donated in this campaign. You can revoke your donation and get back the coins:
   <button @click="undonate">Undonate</button><br/>
   <hr/>
   This campaign is finalized and can be finished. Click <button @click="finish">Finish</button> to finish it, thus the owner can recieve the raised fund.<br/>
   <hr/>
   This campaign has failed but can NOT be finished because still there are some donators need to be returned. Click <button @click="clearDonators">Return</button> to return at most 100 donators' coins.<br/>
   <hr/>
   This campaign has succeeded but can NOT be finished because there are still some donators' records need to be cleared. Click <button @click="clearDonators">Clear</button> to clear at most 100 donators' records.<br/>
   <hr/>
   Click <button @click="donators">Donators</button> to see current donators and their donations. Or click <button @click="history">History</button> to see the history of donations and undonations<br/>
   <hr/>
  </div>
</template>
