```notebook
API.createClient('acmeBankclient', 'b2cbb96c-4219-4752-bb74-e3ec8374971a', 'acme-banking-api', '1.0.2');
```
Retrieve a list of customers.

```notebook
acmeBankclient.customers.get();
```

Retrieve a specific customer information

```notebook
customerA=acmeBankclient.customers.customer_id("8f19cb50-3f57-4d38").get();
```

Retrieve customerA’s displayName

```notebook
customerA.body.displayName
```

Retrieve a specific account information.

```notebook
accountA=acmeBankclient.accounts.account_id("12345").get();
```

Convert accountBalance into a number

```notebook
accountBalanceNumber=Number(accountA.body.accountBalance.amount);
```

Write an if statement to print reward values based on account balance

```notebook
if ( accountBalanceNumber > 5000.00) {
  text = "You will earn 1.5x times the reward for every dollar you spend"; }
else {
  text = "You will earn 1x times the reward for every dollar you spend";
}
text;
```

Write a function to concatenate currency and amount attributes from
the accountBalance property

```notebook
function concatAccountBalance(accountA) {
  return "The accountBalance is "+ accountA.body.accountBalance.currency.concat(" "+ accountA.body.accountBalance.amount);
}
concatAccountBalance(accountA);
```




