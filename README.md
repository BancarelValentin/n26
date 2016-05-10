# Number26 :credit_card:

Un-official node.js module for interact with your number26 account

Open a free [Number26 account here :gift:](https://my.number26.de/?uc=MZMEF)

[![NPM](https://nodei.co/npm/number26.png)](https://nodei.co/npm/number26/)

## What's Number26 ?

> NUMBER26 is Europe's first bank account developed entirely for smartphones. With your NUMBER26 bank account, MasterCard® and mobile app, you can conveniently transfer money from anywhere and keep track of your finances at all times. With MoneyBeam you're able to send money via sms or e-mail without the need to enter all the account details.
>
> There are no costs or fees, which means you can withdraw money at any ATM worldwide, free of charge. No ATM around you? Just use CASH26 to withdraw and deposit cash at your supermarket.

[Open a free account here :gift:](https://my.number26.de/?uc=MZMEF)

## This module

Number26 has some un-official apis.
This module provide you clean functions to interact with your account.

Not all endpoints are available yet.

### WIP :construction:

+ [x] Auth
+ [x] Get account
+ [x] Get cards
+ [x] Get Transactions (with search)
+ [x] Add / update memo on transactions
+ [x] Create a transfert
+ [ ] Get details on transferts
+ [ ] Get / update Settings
+ [ ] ...

### Dependencies

number26 depends on:

+ [bluebird](https://www.npmjs.com/package/bluebird): Bluebird is a full featured promise library with unmatched performance.
+ [request-promise](https://www.npmjs.com/package/request-promise): The world-famous HTTP client 'Request' now Promises/A+ compliant.

### Use :sos:

#### How to install

`npm i number26 --save`

#### Exemple

```JavaScript
var number26 = require('number26');

number26.auth('username@mail.com', 'password')
  .then((account) => account.transactions({text: 'Lafayette'})
  .then((transactions) => {
  /*
    [{
      "id" : "abbc81ce-a5ab-4b5b-a5c2-82541bdb4630",
      "type" : "PT",
      "smartLinkId" : "1125318169-598442",
      "amount" : -21.79,
      "currencyCode" : "EUR",
      "originalAmount" : -21.79,
      "originalCurrency" : "EUR",
      "exchangeRate" : 1.0,
      "merchantCity" : "PARIS",
      "visibleTS" : 1455292872000,
      "mcc" : 5977,
      "mccGroup" : 4,
      "merchantName" : "LAFAYETTE INT.",
      "merchantId" : "970003006643142",
      "recurring" : false,
      "userId" : "8a21b871-0585-481b-ab62-8e3e2d380757",
      "linkId" : "1125318169-598442",
      "accountId" : "5430d368-a0d3-45b3-bcf7-607ece248fa5",
      "category" : "micro-leisure",
      "cardId" : "24f7804b-8a95-4e80-b48a-11fe395ed505",
      "pending" : false,
      "transactionNature" : "NORMAL",
      "confirmed" : 1455494400000
    }]
   */
  });
});
```

#### API

@TODO

### Testing

#### Mocked

> do it, it's safe !

Run `npm test` for full mocked testing with coverage.

[![Build Status](https://travis-ci.org/PierrickP/number26.svg?branch=master)](https://travis-ci.org/PierrickP/number26) [![Coverage Status](https://coveralls.io/repos/github/PierrickP/number26/badge.svg?branch=master)](https://coveralls.io/github/PierrickP/number26?branch=master) [![bitHound Overall Score](https://www.bithound.io/github/PierrickP/number26/badges/score.svg)](https://www.bithound.io/github/PierrickP/number26)

#### :warning: Unmocked :warning:

Less asserts. Used for detect api change.

Run `TEST_EMAIL=exemple@mail.com TEST_PASSWORD=ilovemylittlepony TRANSFER_IBAN=FR7630001007941234567890185 TRANSFER_BIC=BNPAFRPP TRANSFER_NAME="George Loutre" TRANSFER_PIN=123456 npm run test-unmock` for un-mocked test.

The transfer test (*0.01 €) can be switch off with env `NO_TRANSFER`.
Otherwise, *it should be confirmed* in the app.
