# api-php
API PHP


```
$this->aliKassa = new AliKassa(
  '40fe0c0b-0601-4c02-80ee-4100d0040a02',
  'lNiGOZwTvwC4fT36K',
  'md5'
);
```
          
#### Deposit

```
$orderId = time();
$amount = 5000;
$paySystem = 'Qiwi';
$currency = 'RUB';
$desc = 'Test';

$ip = $_SERVER['REMOTE_ADDR'];
$userAgent = $_SERVER['USER_AGENT'];

$response = $this->aliKassa->deposit(
$orderId, $amount, $paySystem, $currency, $desc, $ip, $userAgent,
[
  'phone' => '+79000000000'
]
);
```

##### Response
```
array(2) {
  ["success"]=>
  string(4) "true"
  ["return"]=>
  array(7) {
    ["url"]=>
    string(77) "https://sci.alikassa.com/payment/method?hash=f1500ec036d9c00c0f03afd0020de009"
    ["id"]=>
    string(3) "182"
    ["amount"]=>
    string(4) "5000"
    ["merchantCommission"]=>
    string(12) "400.00000000"
    ["customerCommission"]=>
    string(1) "0"
    ["paySystemAmount"]=>
    string(4) "5000"
    ["merchantBalance"]=>
    string(13) "4600.00000000"
  }
}
```

#### Deposit history
```
$response = $this->aliKassa->depositHistory([
    'page' => 2,
]);

```


