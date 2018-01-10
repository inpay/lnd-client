# Swagger\Client\LightningApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**addInvoice**](LightningApi.md#addInvoice) | **POST** /v1/invoices | * lncli: &#x60;addinvoice&#x60; AddInvoice attempts to add a new invoice to the invoice database. Any duplicated invoices are rejected, therefore all invoices *must* have a unique payment preimage.
[**channelBalance**](LightningApi.md#channelBalance) | **GET** /v1/balance/channels | * lncli: &#x60;channelbalance&#x60; ChannelBalance returns the total funds available across all open channels in satoshis.
[**closeChannel**](LightningApi.md#closeChannel) | **DELETE** /v1/channels/{channel_point.funding_txid}/{channel_point.output_index} | * lncli: &#x60;closechannel&#x60; CloseChannel attempts to close an active channel identified by its channel outpoint (ChannelPoint). The actions of this method can additionally be augmented to attempt a force close after a timeout period in the case of an inactive peer. If a non-force close (cooperative closure) is requested, then the user can specify either a target number of blocks until the closure transaction is confirmed, or a manual fee rate. If neither are specified, then a default lax, block confirmation target is used.
[**connectPeer**](LightningApi.md#connectPeer) | **POST** /v1/peers | * lncli: &#x60;connect&#x60; ConnectPeer attempts to establish a connection to a remote peer. This is at the networking level, and is used for communication between nodes. This is distinct from establishing a channel with a peer.
[**decodePayReq**](LightningApi.md#decodePayReq) | **GET** /v1/payreq/{pay_req} | * lncli: &#x60;decodepayreq&#x60; DecodePayReq takes an encoded payment request string and attempts to decode it, returning a full description of the conditions encoded within the payment request.
[**deleteAllPayments**](LightningApi.md#deleteAllPayments) | **DELETE** /v1/payments | * DeleteAllPayments deletes all outgoing payments from DB.
[**describeGraph**](LightningApi.md#describeGraph) | **GET** /v1/graph | * lncli: &#x60;describegraph&#x60; DescribeGraph returns a description of the latest graph state from the point of view of the node. The graph information is partitioned into two components: all the nodes/vertexes, and all the edges that connect the vertexes themselves.  As this is a directed graph, the edges also contain the node directional specific routing policy which includes: the time lock delta, fee information, etc.
[**disconnectPeer**](LightningApi.md#disconnectPeer) | **DELETE** /v1/peers/{pub_key} | * lncli: &#x60;disconnect&#x60; DisconnectPeer attempts to disconnect one peer from another identified by a given pubKey. In the case that we currently have a pending or active channel with the target peer, then this action will be not be allowed.
[**feeReport**](LightningApi.md#feeReport) | **GET** /v1/fees | * lncli: &#x60;feereport&#x60; FeeReport allows the caller to obtain a report detailing the current fee schedule enforced by the node globally for each channel.
[**getChanInfo**](LightningApi.md#getChanInfo) | **GET** /v1/graph/edge/{chan_id} | * lncli: &#x60;getchaninfo&#x60; GetChanInfo returns the latest authenticated network announcement for the given channel identified by its channel ID: an 8-byte integer which uniquely identifies the location of transaction&#39;s funding output within the blockchain.
[**getInfo**](LightningApi.md#getInfo) | **GET** /v1/getinfo | * lncli: &#x60;getinfo&#x60; GetInfo returns general information concerning the lightning node including it&#39;s identity pubkey, alias, the chains it is connected to, and information concerning the number of open+pending channels.
[**getNetworkInfo**](LightningApi.md#getNetworkInfo) | **GET** /v1/graph/info | * lncli: &#x60;getnetworkinfo&#x60; GetNetworkInfo returns some basic stats about the known channel graph from the point of view of the node.
[**getNodeInfo**](LightningApi.md#getNodeInfo) | **GET** /v1/graph/node/{pub_key} | * lncli: &#x60;getnodeinfo&#x60; GetNodeInfo returns the latest advertised, aggregated, and authenticated channel information for the specified node identified by its public key.
[**getTransactions**](LightningApi.md#getTransactions) | **GET** /v1/transactions | * lncli: &#x60;listchaintxns&#x60; GetTransactions returns a list describing all the known transactions relevant to the wallet.
[**listChannels**](LightningApi.md#listChannels) | **GET** /v1/channels | * lncli: &#x60;listchannels&#x60; ListChannels returns a description of all the open channels that this node is a participant in.
[**listInvoices**](LightningApi.md#listInvoices) | **GET** /v1/invoices/{pending_only} | * lncli: &#x60;listinvoices&#x60; ListInvoices returns a list of all the invoices currently stored within the database. Any active debug invoices are ignored.
[**listPayments**](LightningApi.md#listPayments) | **GET** /v1/payments | * lncli: &#x60;listpayments&#x60; ListPayments returns a list of all outgoing payments.
[**listPeers**](LightningApi.md#listPeers) | **GET** /v1/peers | * lncli: &#x60;listpeers&#x60; ListPeers returns a verbose listing of all currently active peers.
[**lookupInvoice**](LightningApi.md#lookupInvoice) | **GET** /v1/invoices/{r_hash_str} | * lncli: &#x60;lookupinvoice&#x60; LookupInvoice attemps to look up an invoice according to its payment hash. The passed payment hash *must* be exactly 32 bytes, if not, an error is returned.
[**newWitnessAddress**](LightningApi.md#newWitnessAddress) | **GET** /v1/newaddress | * NewWitnessAddress creates a new witness address under control of the local wallet.
[**openChannelSync**](LightningApi.md#openChannelSync) | **POST** /v1/channels | * OpenChannelSync is a synchronous version of the OpenChannel RPC call. This call is meant to be consumed by clients to the REST proxy. As with all other sync calls, all byte slices are intended to be populated as hex encoded strings.
[**pendingChannels**](LightningApi.md#pendingChannels) | **GET** /v1/channels/pending | * lncli: &#x60;pendingchannels&#x60; PendingChannels returns a list of all the channels that are currently considered \&quot;pending\&quot;. A channel is pending if it has finished the funding workflow and is waiting for confirmations for the funding txn, or is in the process of closure, either initiated cooperatively or non-cooperatively.
[**queryRoutes**](LightningApi.md#queryRoutes) | **GET** /v1/graph/routes/{pub_key}/{amt} | * lncli: &#x60;queryroutes&#x60; QueryRoutes attempts to query the daemon&#39;s Channel Router for a possible route to a target destination capable of carrying a specific amount of satoshis. The retuned route contains the full details required to craft and send an HTLC, also including the necessary information that should be present within the Sphinx packet encapsualted within the HTLC.
[**sendCoins**](LightningApi.md#sendCoins) | **POST** /v1/transactions | * lncli: &#x60;sendcoins&#x60; SendCoins executes a request to send coins to a particular address. Unlike SendMany, this RPC call only allows creating a single output at a time. If neither target_conf, or sat_per_byte are set, then the internal wallet will consult its fee model to determine a fee for the default confirmation target.
[**sendPaymentSync**](LightningApi.md#sendPaymentSync) | **POST** /v1/channels/transactions | * SendPaymentSync is the synchronous non-streaming version of SendPayment. This RPC is intended to be consumed by clients of the REST proxy. Additionally, this RPC expects the destination&#39;s public key and the payment hash (if any) to be encoded as hex strings.
[**subscribeInvoices**](LightningApi.md#subscribeInvoices) | **GET** /v1/invoices/subscribe | * SubscribeInvoices returns a uni-directional stream (sever -&gt; client) for notifying the client of newly added/settled invoices.
[**updateFees**](LightningApi.md#updateFees) | **POST** /v1/fees | * lncli: &#x60;updatefees&#x60; UpdateFees allows the caller to update the fee schedule for all channels globally, or a particular channel.
[**walletBalance**](LightningApi.md#walletBalance) | **GET** /v1/balance/blockchain | * lncli: &#x60;walletbalance&#x60; WalletBalance returns total unspent outputs(confirmed and unconfirmed), all confirmed unspent outputs and all unconfirmed unspent outputs under control by the wallet. This method can be modified by having the request specify only witness outputs should be factored into the final output sum.


# **addInvoice**
> \Swagger\Client\Model\AddInvoiceResponse addInvoice($body)

* lncli: `addinvoice` AddInvoice attempts to add a new invoice to the invoice database. Any duplicated invoices are rejected, therefore all invoices *must* have a unique payment preimage.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\Invoice(); // \Swagger\Client\Model\Invoice | 

try {
    $result = $apiInstance->addInvoice($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->addInvoice: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\Invoice**](../Model/Invoice.md)|  |

### Return type

[**\Swagger\Client\Model\AddInvoiceResponse**](../Model/AddInvoiceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **channelBalance**
> \Swagger\Client\Model\ChannelBalanceResponse channelBalance()

* lncli: `channelbalance` ChannelBalance returns the total funds available across all open channels in satoshis.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->channelBalance();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->channelBalance: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\ChannelBalanceResponse**](../Model/ChannelBalanceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **closeChannel**
> \Swagger\Client\Model\CloseStatusUpdate closeChannel($channel_point_funding_txid, $channel_point_output_index)

* lncli: `closechannel` CloseChannel attempts to close an active channel identified by its channel outpoint (ChannelPoint). The actions of this method can additionally be augmented to attempt a force close after a timeout period in the case of an inactive peer. If a non-force close (cooperative closure) is requested, then the user can specify either a target number of blocks until the closure transaction is confirmed, or a manual fee rate. If neither are specified, then a default lax, block confirmation target is used.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$channel_point_funding_txid = "B"; // string | 
$channel_point_output_index = 789; // int | 

try {
    $result = $apiInstance->closeChannel($channel_point_funding_txid, $channel_point_output_index);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->closeChannel: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **channel_point_funding_txid** | **string**|  |
 **channel_point_output_index** | **int**|  |

### Return type

[**\Swagger\Client\Model\CloseStatusUpdate**](../Model/CloseStatusUpdate.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **connectPeer**
> \Swagger\Client\Model\ConnectPeerResponse connectPeer($body)

* lncli: `connect` ConnectPeer attempts to establish a connection to a remote peer. This is at the networking level, and is used for communication between nodes. This is distinct from establishing a channel with a peer.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\ConnectPeerRequest(); // \Swagger\Client\Model\ConnectPeerRequest | 

try {
    $result = $apiInstance->connectPeer($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->connectPeer: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\ConnectPeerRequest**](../Model/ConnectPeerRequest.md)|  |

### Return type

[**\Swagger\Client\Model\ConnectPeerResponse**](../Model/ConnectPeerResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **decodePayReq**
> \Swagger\Client\Model\PayReq decodePayReq($pay_req)

* lncli: `decodepayreq` DecodePayReq takes an encoded payment request string and attempts to decode it, returning a full description of the conditions encoded within the payment request.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$pay_req = "pay_req_example"; // string | 

try {
    $result = $apiInstance->decodePayReq($pay_req);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->decodePayReq: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pay_req** | **string**|  |

### Return type

[**\Swagger\Client\Model\PayReq**](../Model/PayReq.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **deleteAllPayments**
> \Swagger\Client\Model\DeleteAllPaymentsResponse deleteAllPayments()

* DeleteAllPayments deletes all outgoing payments from DB.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->deleteAllPayments();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->deleteAllPayments: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\DeleteAllPaymentsResponse**](../Model/DeleteAllPaymentsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **describeGraph**
> \Swagger\Client\Model\ChannelGraph describeGraph()

* lncli: `describegraph` DescribeGraph returns a description of the latest graph state from the point of view of the node. The graph information is partitioned into two components: all the nodes/vertexes, and all the edges that connect the vertexes themselves.  As this is a directed graph, the edges also contain the node directional specific routing policy which includes: the time lock delta, fee information, etc.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->describeGraph();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->describeGraph: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\ChannelGraph**](../Model/ChannelGraph.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **disconnectPeer**
> \Swagger\Client\Model\DisconnectPeerResponse disconnectPeer($pub_key)

* lncli: `disconnect` DisconnectPeer attempts to disconnect one peer from another identified by a given pubKey. In the case that we currently have a pending or active channel with the target peer, then this action will be not be allowed.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$pub_key = "pub_key_example"; // string | 

try {
    $result = $apiInstance->disconnectPeer($pub_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->disconnectPeer: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pub_key** | **string**|  |

### Return type

[**\Swagger\Client\Model\DisconnectPeerResponse**](../Model/DisconnectPeerResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **feeReport**
> \Swagger\Client\Model\FeeReportResponse feeReport()

* lncli: `feereport` FeeReport allows the caller to obtain a report detailing the current fee schedule enforced by the node globally for each channel.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->feeReport();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->feeReport: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\FeeReportResponse**](../Model/FeeReportResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getChanInfo**
> \Swagger\Client\Model\ChannelEdge getChanInfo($chan_id)

* lncli: `getchaninfo` GetChanInfo returns the latest authenticated network announcement for the given channel identified by its channel ID: an 8-byte integer which uniquely identifies the location of transaction's funding output within the blockchain.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$chan_id = "chan_id_example"; // string | 

try {
    $result = $apiInstance->getChanInfo($chan_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->getChanInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **chan_id** | **string**|  |

### Return type

[**\Swagger\Client\Model\ChannelEdge**](../Model/ChannelEdge.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getInfo**
> \Swagger\Client\Model\GetInfoResponse getInfo()

* lncli: `getinfo` GetInfo returns general information concerning the lightning node including it's identity pubkey, alias, the chains it is connected to, and information concerning the number of open+pending channels.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getInfo();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->getInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\GetInfoResponse**](../Model/GetInfoResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getNetworkInfo**
> \Swagger\Client\Model\NetworkInfo getNetworkInfo()

* lncli: `getnetworkinfo` GetNetworkInfo returns some basic stats about the known channel graph from the point of view of the node.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getNetworkInfo();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->getNetworkInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\NetworkInfo**](../Model/NetworkInfo.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getNodeInfo**
> \Swagger\Client\Model\NodeInfo getNodeInfo($pub_key)

* lncli: `getnodeinfo` GetNodeInfo returns the latest advertised, aggregated, and authenticated channel information for the specified node identified by its public key.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$pub_key = "pub_key_example"; // string | 

try {
    $result = $apiInstance->getNodeInfo($pub_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->getNodeInfo: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pub_key** | **string**|  |

### Return type

[**\Swagger\Client\Model\NodeInfo**](../Model/NodeInfo.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **getTransactions**
> \Swagger\Client\Model\TransactionDetails getTransactions()

* lncli: `listchaintxns` GetTransactions returns a list describing all the known transactions relevant to the wallet.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->getTransactions();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->getTransactions: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\TransactionDetails**](../Model/TransactionDetails.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listChannels**
> \Swagger\Client\Model\ListChannelsResponse listChannels()

* lncli: `listchannels` ListChannels returns a description of all the open channels that this node is a participant in.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->listChannels();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->listChannels: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\ListChannelsResponse**](../Model/ListChannelsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listInvoices**
> \Swagger\Client\Model\ListInvoiceResponse listInvoices($pending_only)

* lncli: `listinvoices` ListInvoices returns a list of all the invoices currently stored within the database. Any active debug invoices are ignored.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$pending_only = true; // bool | 

try {
    $result = $apiInstance->listInvoices($pending_only);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->listInvoices: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pending_only** | **bool**|  |

### Return type

[**\Swagger\Client\Model\ListInvoiceResponse**](../Model/ListInvoiceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listPayments**
> \Swagger\Client\Model\ListPaymentsResponse listPayments()

* lncli: `listpayments` ListPayments returns a list of all outgoing payments.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->listPayments();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->listPayments: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\ListPaymentsResponse**](../Model/ListPaymentsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **listPeers**
> \Swagger\Client\Model\ListPeersResponse listPeers()

* lncli: `listpeers` ListPeers returns a verbose listing of all currently active peers.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->listPeers();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->listPeers: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\ListPeersResponse**](../Model/ListPeersResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **lookupInvoice**
> \Swagger\Client\Model\Invoice lookupInvoice($r_hash_str, $r_hash)

* lncli: `lookupinvoice` LookupInvoice attemps to look up an invoice according to its payment hash. The passed payment hash *must* be exactly 32 bytes, if not, an error is returned.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$r_hash_str = "r_hash_str_example"; // string | 
$r_hash = "B"; // string | / The payment hash of the invoice to be looked up.

try {
    $result = $apiInstance->lookupInvoice($r_hash_str, $r_hash);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->lookupInvoice: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **r_hash_str** | **string**|  |
 **r_hash** | **string**| / The payment hash of the invoice to be looked up. | [optional]

### Return type

[**\Swagger\Client\Model\Invoice**](../Model/Invoice.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **newWitnessAddress**
> \Swagger\Client\Model\NewAddressResponse newWitnessAddress()

* NewWitnessAddress creates a new witness address under control of the local wallet.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->newWitnessAddress();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->newWitnessAddress: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\NewAddressResponse**](../Model/NewAddressResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **openChannelSync**
> \Swagger\Client\Model\ChannelPoint openChannelSync($body)

* OpenChannelSync is a synchronous version of the OpenChannel RPC call. This call is meant to be consumed by clients to the REST proxy. As with all other sync calls, all byte slices are intended to be populated as hex encoded strings.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\OpenChannelRequest(); // \Swagger\Client\Model\OpenChannelRequest | 

try {
    $result = $apiInstance->openChannelSync($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->openChannelSync: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\OpenChannelRequest**](../Model/OpenChannelRequest.md)|  |

### Return type

[**\Swagger\Client\Model\ChannelPoint**](../Model/ChannelPoint.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **pendingChannels**
> \Swagger\Client\Model\PendingChannelResponse pendingChannels()

* lncli: `pendingchannels` PendingChannels returns a list of all the channels that are currently considered \"pending\". A channel is pending if it has finished the funding workflow and is waiting for confirmations for the funding txn, or is in the process of closure, either initiated cooperatively or non-cooperatively.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->pendingChannels();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->pendingChannels: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\PendingChannelResponse**](../Model/PendingChannelResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **queryRoutes**
> \Swagger\Client\Model\QueryRoutesResponse queryRoutes($pub_key, $amt)

* lncli: `queryroutes` QueryRoutes attempts to query the daemon's Channel Router for a possible route to a target destination capable of carrying a specific amount of satoshis. The retuned route contains the full details required to craft and send an HTLC, also including the necessary information that should be present within the Sphinx packet encapsualted within the HTLC.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$pub_key = "pub_key_example"; // string | 
$amt = "amt_example"; // string | 

try {
    $result = $apiInstance->queryRoutes($pub_key, $amt);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->queryRoutes: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **pub_key** | **string**|  |
 **amt** | **string**|  |

### Return type

[**\Swagger\Client\Model\QueryRoutesResponse**](../Model/QueryRoutesResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **sendCoins**
> \Swagger\Client\Model\SendCoinsResponse sendCoins($body)

* lncli: `sendcoins` SendCoins executes a request to send coins to a particular address. Unlike SendMany, this RPC call only allows creating a single output at a time. If neither target_conf, or sat_per_byte are set, then the internal wallet will consult its fee model to determine a fee for the default confirmation target.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\SendCoinsRequest(); // \Swagger\Client\Model\SendCoinsRequest | 

try {
    $result = $apiInstance->sendCoins($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->sendCoins: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\SendCoinsRequest**](../Model/SendCoinsRequest.md)|  |

### Return type

[**\Swagger\Client\Model\SendCoinsResponse**](../Model/SendCoinsResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **sendPaymentSync**
> \Swagger\Client\Model\SendResponse sendPaymentSync($body)

* SendPaymentSync is the synchronous non-streaming version of SendPayment. This RPC is intended to be consumed by clients of the REST proxy. Additionally, this RPC expects the destination's public key and the payment hash (if any) to be encoded as hex strings.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\SendRequest(); // \Swagger\Client\Model\SendRequest | 

try {
    $result = $apiInstance->sendPaymentSync($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->sendPaymentSync: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\SendRequest**](../Model/SendRequest.md)|  |

### Return type

[**\Swagger\Client\Model\SendResponse**](../Model/SendResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **subscribeInvoices**
> \Swagger\Client\Model\Invoice subscribeInvoices()

* SubscribeInvoices returns a uni-directional stream (sever -> client) for notifying the client of newly added/settled invoices.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->subscribeInvoices();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->subscribeInvoices: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\Invoice**](../Model/Invoice.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **updateFees**
> \Swagger\Client\Model\FeeUpdateResponse updateFees($body)

* lncli: `updatefees` UpdateFees allows the caller to update the fee schedule for all channels globally, or a particular channel.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$body = new \Swagger\Client\Model\FeeUpdateRequest(); // \Swagger\Client\Model\FeeUpdateRequest | 

try {
    $result = $apiInstance->updateFees($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->updateFees: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**\Swagger\Client\Model\FeeUpdateRequest**](../Model/FeeUpdateRequest.md)|  |

### Return type

[**\Swagger\Client\Model\FeeUpdateResponse**](../Model/FeeUpdateResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **walletBalance**
> \Swagger\Client\Model\WalletBalanceResponse walletBalance($witness_only)

* lncli: `walletbalance` WalletBalance returns total unspent outputs(confirmed and unconfirmed), all confirmed unspent outputs and all unconfirmed unspent outputs under control by the wallet. This method can be modified by having the request specify only witness outputs should be factored into the final output sum.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$apiInstance = new Swagger\Client\Api\LightningApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$witness_only = true; // bool | / If only witness outputs should be considered when calculating the wallet's balance.

try {
    $result = $apiInstance->walletBalance($witness_only);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling LightningApi->walletBalance: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **witness_only** | **bool**| / If only witness outputs should be considered when calculating the wallet&#39;s balance. | [optional]

### Return type

[**\Swagger\Client\Model\WalletBalanceResponse**](../Model/WalletBalanceResponse.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

