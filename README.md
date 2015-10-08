# Aliyun MNS

This is an unofficial SDK for Aliyun MNS (MQS).

*Thought it work fine, I do not like it at all and may rewrite it when I'm have time.*

## Installation

This package can be installed through `composer`.

```bash
composer require ripples/aliyun-mns
```

## Usage

```php
use Ripples\Aliyun\MNS;

$client = new MNS([
    'accessKeyId' => 'accessKeyId',
    'accessKeySecret' => 'accessKeySecret',
    'accessOwnerId' => 'transformQueueOwner',
    'accessRegion' => 'transformQueueRegion',
    'accessQueue' => 'transformQueueName',
]);

$client->sendMessage([
    'MessageBody' => 'A message.',
    'DelaySeconds' => 0,
    'Priority' => 8
]);

$msg = $client->receiveMessage();

$client->dropMessage([
    'ReceiptHandle' => '1-ODU4OTkzNDU5My0xNDA1ODQ4OTUwLTItOA=='
]);
```

## LICENSE
[MIT](./LICENSE)
