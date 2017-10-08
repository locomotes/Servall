# Servall Blockhack MVP Intro & Overview

The Servall team won first place at the 2017 Lincoln Blockchain Hackathon at the Duke University School of Law. The native mobile app was designed and developed in 48 hours. The project serves as a proof of concept for a public ledger that tracks the distribution of charitable donations. The team used the Litecoin protocol and React native for the front-end. 

<table>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall.png" />
    </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (1).png" />
    </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (2).png" />
    </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (3).png" />
    </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (4).png" />
    </td>
  </tr>
   <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (5).png" />
    </td>
  </tr>
   <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (6).png" />
    </td>
  </tr>
   <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (7).png" />
    </td>
  </tr>
   <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/Servall (8).png" />
    </td>
  </tr>
  
</table>

# Servall Blockhack Product Spec

*"public ledger to track the distribution of charitable donations"*

## Intro & Goal

Our goal is to bring transparency to the distribution of charitable donations. 

The problem is that money is oftentimes given to charity and the donor has no idea how their contribution is allocated. Who are the recipients of the donated funds? How much of the original donation made it to people in need? By recording all charitable transactions on the blockchain, we’ll have a public ledger where donors can track the distribution of funds. 

## Who’s it for?

1. **Charitable donors** - those who give to support charitable causes and want transparency into how the money is being allocated.

2. **Charitable recipients** - those on the receiving end of charitable donations who want an easy way to apply for and accepts funds. 

## Why build it?

1. Bringing transparency to the process of helping those in need is a cause that we are passionate about. 

2. Donors want to know what happens to their funds after they give. Forty-one percent of donors say that increased knowledge or transparency into nonprofit effectiveness has impacted their personal approach to giving.*

3. Proof of concept (example nonprofit) for using blockchain to drive innovation in the nonprofit industry.

4. The tech risk is low

* Nonprofit business advisor: [Transparency, technology top list of trends influencing individual donor behaviors](http://onlinelibrary.wiley.com/doi/10.1002/nba.30259/full). First published: 23 November 2016

## What is it?

Native mobile application that records, displays, and manages exchanges between charitable donors and recipients.

**User Types**

1. **Donors**: Users that have created accounts for the purpose of making donations. 

2. **Prospective recipients**: Users that have created accounts to they can apply to receive donations. 

3. **Approved recipients**: Users that have been approved to receive donations.  

**Addresses**

1. **Aggregate donation address**: This the litecoin address that sends all donations. 

2. **Administration address**: This is the litecoin address that collects the administrative fees. 

3. **Aggregate recipient address**: This the litecoin address that receives all donations.

**What we are doing today**

A donor sends us USD via Stripe to our admin account. When this is received, we send a representative amount 0.01 LTC = $1 to our aggregate recipient address. When it becomes time to allocate funds to a recipient, we randomly pick a user from our database and send them a pending request that they have funds to redeem. The recipient enters their thank you message, and we will send a Stripe transaction from our admin account to the recipient’s account. At the same time, we send another representative amount back to aggregated donation address. 

**What we plan on doing**

Would use op_return to hold the transactional data of the donation. This would be the donor message with Stripe transaction id, identifier for our database and the amount (privatedbID, StripeTXID, amount). Bitcoin and litecoin have op_return. However, we would create our own coin so we would not have to pay the transaction cost. The coin would not incentivise mining. We’d control all the coins, and the value of the coin would be representative of the US dollar but would not be redeemable. 

<table>
  <tr>
    <td> 
    <strong>Sign Up View</strong>

Create an account and login with facebook. </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/SERVALL_UI-10.png" width="250px"/>
    </td>
  </tr>
</table>


<table>
  <tr>
    <td>
    <strong>Threads</strong>

Venmo-like timeline view where users can see a feed of all transactions taking place between donors and recipients.

Filters for just the users transactions (Me), transactions of the user’s Facebook friends (Friends), and all transactions (Public). </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/SERVALL_UI-11.png" width="250px"/>
    </td>
  </tr>
</table>


<table>
  <tr>
    <td> 
    <strong>Profile View</strong>

This would be a profile view for a user who can both donate AND receive funds. 

When users sign up for accounts, they will default to donors ONLY. There will be an option to apply for the user right to receive funds. </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/SERVALL_UI-12.png" width="250px"/>
    </td>
  </tr>
</table>


<table>
  <tr>
    <td>
    <strong>Donate View</strong>

When a user clicks a CTA to donate, they will be presented with this view. 

Total displayed at the top is the aggregate dollar amount donated since the user created an account.

There will be a numeric input for the donation amount. Also, there will be a text field for the donor to add a message for the recipient user. </td>
  </tr>
  <tr>
   <td>
    <img src="https://locomotes.github.io/Servall/images/SERVALL_UI-13.png" width="250"/>
    </td>
  </tr>
</table>


<table>
  <tr>
    <td> 
    <strong>Recipient View</strong>

When a user donation is submitted, the recipient will be presented with this view in order to receive the funds. 

Total displayed at the top is the aggregate dollar amount of donations received since the user created an account.

There will be a text field for the recipient to add a thank you message for the donor user. </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/SERVALL_UI-14.png" width="250"/>
    </td>
  </tr>
</table>


<table>
  <tr>
    <td> 
    <strong>Thank You Donor View</strong>

Once the recipient submits their thank you message, the donor is directed to their thank you view. 

Here the donor can read the recipient’s thank you message and understand how their donation was put to use. </td>
  </tr>
  <tr>
  <td>
    <img src="https://locomotes.github.io/Servall/images/SERVALL_UI-15.png" width="250"/>
    </td>
  </tr>
</table>


## Brand

**Name**

Inspiration from a region that we want to serve. The serval is a wild cat native to Africa.

**Visual Language**

**Typeface:** MULI - https://fonts.google.com/specimen/Muli 

**Color Palette**

**Dark Blue (Information): #392f2c**

	Dark Blue 80%: #5d5351

	Dark Blue 40%: #aba5a3

	Dark Blue 10%: #392f2c

**Blue (Transparency): #57c1e8**

	Blue 80%: #82cded

	Blue 40%: #c5e6f6

	Blue 10%: #f1f8fc

**Turquoise (Growth): #83c8bc**

	Turquoise 80%: #9dd3c9

	Turquoise 40%: #cfe9e3

	Turquoise 10%: #f4f9f7

**Pink (Passion): #ff7175**

	Pink 80%: #ff938f

	Pink 40%: #ffccc5

	Pink 10%: #fff2ef

**Sand (Quilt): #eca55d**

	Sand 80%: #f2b77d;

	Sand 40%: #fcdabc;

	Sand 10%: #fff5ed
