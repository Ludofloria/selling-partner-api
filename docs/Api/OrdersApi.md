# SellingPartnerApi\OrdersApi

All URIs are relative to https://sellingpartnerapi-na.amazon.com.

Method | HTTP request | Description
------------- | ------------- | -------------
[**getOrder()**](OrdersApi.md#getOrder) | **GET** /orders/v0/orders/{orderId} | 
[**getOrderAddress()**](OrdersApi.md#getOrderAddress) | **GET** /orders/v0/orders/{orderId}/address | 
[**getOrderBuyerInfo()**](OrdersApi.md#getOrderBuyerInfo) | **GET** /orders/v0/orders/{orderId}/buyerInfo | 
[**getOrderItems()**](OrdersApi.md#getOrderItems) | **GET** /orders/v0/orders/{orderId}/orderItems | 
[**getOrderItemsBuyerInfo()**](OrdersApi.md#getOrderItemsBuyerInfo) | **GET** /orders/v0/orders/{orderId}/orderItems/buyerInfo | 
[**getOrders()**](OrdersApi.md#getOrders) | **GET** /orders/v0/orders | 


## `getOrder()`

```php
getOrder($order_id): \SellingPartnerApi\Model\Orders\GetOrderResponse
```



Returns the order indicated by the specified order ID.  **Usage Plan:**  | Rate (requests per second) | Burst | | ---- | ---- | | 1 | 1 |  For more information, see \"Usage Plans and Rate Limits\" in the Selling Partner API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// See README for more information on the ConfigurationOptions object
$configurationOptions = new SellingPartnerApi\ConfigurationOptions(
    "amzn1.application-oa2-client.....",
    "abcd....",
    "Aztr|IwEBI....",
    "AKIA....",
    "ABCD....",
    "us-east-1",
    "https://sellingpartnerapi-na.amazon.com",
);
$config = new SellingPartnerApi\Configuration($configurationOptions);

$apiInstance = new SellingPartnerApi\Api\OrdersApi($config);
$order_id = 'order_id_example'; // string | An Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrder($order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getOrder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **string**| An Amazon-defined order identifier, in 3-7-7 format. |

### Return type

[**\SellingPartnerApi\Model\Orders\GetOrderResponse**](../Model/Orders/GetOrderResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Top]](#) [[API list]](../)
[[Orders Model list]](../Model/Orders)
[[README]](../../README.md)

## `getOrderAddress()`

```php
getOrderAddress($order_id): \SellingPartnerApi\Model\Orders\GetOrderAddressResponse
```



Returns the shipping address for the order indicated by the specified order ID.  **Usage Plan:**  | Rate (requests per second) | Burst | | ---- | ---- | | 1 | 1 |  For more information, see \"Usage Plans and Rate Limits\" in the Selling Partner API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// See README for more information on the ConfigurationOptions object
$configurationOptions = new SellingPartnerApi\ConfigurationOptions(
    "amzn1.application-oa2-client.....",
    "abcd....",
    "Aztr|IwEBI....",
    "AKIA....",
    "ABCD....",
    "us-east-1",
    "https://sellingpartnerapi-na.amazon.com",
);
$config = new SellingPartnerApi\Configuration($configurationOptions);

$apiInstance = new SellingPartnerApi\Api\OrdersApi($config);
$order_id = 'order_id_example'; // string | An orderId is an Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrderAddress($order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getOrderAddress: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **string**| An orderId is an Amazon-defined order identifier, in 3-7-7 format. |

### Return type

[**\SellingPartnerApi\Model\Orders\GetOrderAddressResponse**](../Model/Orders/GetOrderAddressResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Top]](#) [[API list]](../)
[[Orders Model list]](../Model/Orders)
[[README]](../../README.md)

## `getOrderBuyerInfo()`

```php
getOrderBuyerInfo($order_id): \SellingPartnerApi\Model\Orders\GetOrderBuyerInfoResponse
```



Returns buyer information for the order indicated by the specified order ID.  **Usage Plan:**  | Rate (requests per second) | Burst | | ---- | ---- | | 1 | 1 |  For more information, see \"Usage Plans and Rate Limits\" in the Selling Partner API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// See README for more information on the ConfigurationOptions object
$configurationOptions = new SellingPartnerApi\ConfigurationOptions(
    "amzn1.application-oa2-client.....",
    "abcd....",
    "Aztr|IwEBI....",
    "AKIA....",
    "ABCD....",
    "us-east-1",
    "https://sellingpartnerapi-na.amazon.com",
);
$config = new SellingPartnerApi\Configuration($configurationOptions);

$apiInstance = new SellingPartnerApi\Api\OrdersApi($config);
$order_id = 'order_id_example'; // string | An orderId is an Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrderBuyerInfo($order_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getOrderBuyerInfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **string**| An orderId is an Amazon-defined order identifier, in 3-7-7 format. |

### Return type

[**\SellingPartnerApi\Model\Orders\GetOrderBuyerInfoResponse**](../Model/Orders/GetOrderBuyerInfoResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Top]](#) [[API list]](../)
[[Orders Model list]](../Model/Orders)
[[README]](../../README.md)

## `getOrderItems()`

```php
getOrderItems($order_id, $next_token): \SellingPartnerApi\Model\Orders\GetOrderItemsResponse
```



Returns detailed order item information for the order indicated by the specified order ID. If NextToken is provided, it's used to retrieve the next page of order items.  Note: When an order is in the Pending state (the order has been placed but payment has not been authorized), the getOrderItems operation does not return information about pricing, taxes, shipping charges, gift status or promotions for the order items in the order. After an order leaves the Pending state (this occurs when payment has been authorized) and enters the Unshipped, Partially Shipped, or Shipped state, the getOrderItems operation returns information about pricing, taxes, shipping charges, gift status and promotions for the order items in the order.  **Usage Plan:**  | Rate (requests per second) | Burst | | ---- | ---- | | 1 | 1 |  For more information, see \"Usage Plans and Rate Limits\" in the Selling Partner API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// See README for more information on the ConfigurationOptions object
$configurationOptions = new SellingPartnerApi\ConfigurationOptions(
    "amzn1.application-oa2-client.....",
    "abcd....",
    "Aztr|IwEBI....",
    "AKIA....",
    "ABCD....",
    "us-east-1",
    "https://sellingpartnerapi-na.amazon.com",
);
$config = new SellingPartnerApi\Configuration($configurationOptions);

$apiInstance = new SellingPartnerApi\Api\OrdersApi($config);
$order_id = 'order_id_example'; // string | An Amazon-defined order identifier, in 3-7-7 format.
$next_token = 'next_token_example'; // string | A string token returned in the response of your previous request.

try {
    $result = $apiInstance->getOrderItems($order_id, $next_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getOrderItems: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **string**| An Amazon-defined order identifier, in 3-7-7 format. |
 **next_token** | **string**| A string token returned in the response of your previous request. | [optional]

### Return type

[**\SellingPartnerApi\Model\Orders\GetOrderItemsResponse**](../Model/Orders/GetOrderItemsResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Top]](#) [[API list]](../)
[[Orders Model list]](../Model/Orders)
[[README]](../../README.md)

## `getOrderItemsBuyerInfo()`

```php
getOrderItemsBuyerInfo($order_id, $next_token): \SellingPartnerApi\Model\Orders\GetOrderItemsBuyerInfoResponse
```



Returns buyer information in the order items of the order indicated by the specified order ID.  **Usage Plan:**  | Rate (requests per second) | Burst | | ---- | ---- | | 1 | 1 |  For more information, see \"Usage Plans and Rate Limits\" in the Selling Partner API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// See README for more information on the ConfigurationOptions object
$configurationOptions = new SellingPartnerApi\ConfigurationOptions(
    "amzn1.application-oa2-client.....",
    "abcd....",
    "Aztr|IwEBI....",
    "AKIA....",
    "ABCD....",
    "us-east-1",
    "https://sellingpartnerapi-na.amazon.com",
);
$config = new SellingPartnerApi\Configuration($configurationOptions);

$apiInstance = new SellingPartnerApi\Api\OrdersApi($config);
$order_id = 'order_id_example'; // string | An Amazon-defined order identifier, in 3-7-7 format.
$next_token = 'next_token_example'; // string | A string token returned in the response of your previous request.

try {
    $result = $apiInstance->getOrderItemsBuyerInfo($order_id, $next_token);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getOrderItemsBuyerInfo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **order_id** | **string**| An Amazon-defined order identifier, in 3-7-7 format. |
 **next_token** | **string**| A string token returned in the response of your previous request. | [optional]

### Return type

[**\SellingPartnerApi\Model\Orders\GetOrderItemsBuyerInfoResponse**](../Model/Orders/GetOrderItemsBuyerInfoResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Top]](#) [[API list]](../)
[[Orders Model list]](../Model/Orders)
[[README]](../../README.md)

## `getOrders()`

```php
getOrders($marketplace_ids, $created_after, $created_before, $last_updated_after, $last_updated_before, $order_statuses, $fulfillment_channels, $payment_methods, $buyer_email, $seller_order_id, $max_results_per_page, $easy_ship_shipment_statuses, $next_token, $amazon_order_ids): \SellingPartnerApi\Model\Orders\GetOrdersResponse
```



Returns orders created or updated during the time frame indicated by the specified parameters. You can also apply a range of filtering criteria to narrow the list of orders returned. If NextToken is present, that will be used to retrieve the orders instead of other criteria.  **Usage Plan:**  | Rate (requests per second) | Burst | | ---- | ---- | | 1 | 1 |  For more information, see \"Usage Plans and Rate Limits\" in the Selling Partner API documentation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

// See README for more information on the ConfigurationOptions object
$configurationOptions = new SellingPartnerApi\ConfigurationOptions(
    "amzn1.application-oa2-client.....",
    "abcd....",
    "Aztr|IwEBI....",
    "AKIA....",
    "ABCD....",
    "us-east-1",
    "https://sellingpartnerapi-na.amazon.com",
);
$config = new SellingPartnerApi\Configuration($configurationOptions);

$apiInstance = new SellingPartnerApi\Api\OrdersApi($config);
$marketplace_ids = array('marketplace_ids_example'); // string[] | A list of MarketplaceId values. Used to select orders that were placed in the specified marketplaces.
$created_after = 'created_after_example'; // string | A date used for selecting orders created after (or at) a specified time. Only orders placed after the specified time are returned. Either the CreatedAfter parameter or the LastUpdatedAfter parameter is required. Both cannot be empty. The date must be in ISO 8601 format.
$created_before = 'created_before_example'; // string | A date used for selecting orders created before (or at) a specified time. Only orders placed before the specified time are returned. The date must be in ISO 8601 format.
$last_updated_after = 'last_updated_after_example'; // string | A date used for selecting orders that were last updated after (or at) a specified time. An update is defined as any change in order status, including the creation of a new order. Includes updates made by Amazon and by the seller. The date must be in ISO 8601 format.
$last_updated_before = 'last_updated_before_example'; // string | A date used for selecting orders that were last updated before (or at) a specified time. An update is defined as any change in order status, including the creation of a new order. Includes updates made by Amazon and by the seller. The date must be in ISO 8601 format.
$order_statuses = array('order_statuses_example'); // string[] | A list of OrderStatus values used to filter the results. Possible values: PendingAvailability (This status is available for pre-orders only. The order has been placed, payment has not been authorized, and the release date of the item is in the future.); Pending (The order has been placed but payment has not been authorized); Unshipped (Payment has been authorized and the order is ready for shipment, but no items in the order have been shipped); PartiallyShipped (One or more, but not all, items in the order have been shipped); Shipped (All items in the order have been shipped); InvoiceUnconfirmed (All items in the order have been shipped. The seller has not yet given confirmation to Amazon that the invoice has been shipped to the buyer.); Canceled (The order has been canceled); and Unfulfillable (The order cannot be fulfilled. This state applies only to Multi-Channel Fulfillment orders.).
$fulfillment_channels = array('fulfillment_channels_example'); // string[] | A list that indicates how an order was fulfilled. Filters the results by fulfillment channel. Possible values: FBA (Fulfillment by Amazon); SellerFulfilled (Fulfilled by the seller).
$payment_methods = array('payment_methods_example'); // string[] | A list of payment method values. Used to select orders paid using the specified payment methods. Possible values: COD (Cash on delivery); CVS (Convenience store payment); Other (Any payment method other than COD or CVS).
$buyer_email = 'buyer_email_example'; // string | The email address of a buyer. Used to select orders that contain the specified email address.
$seller_order_id = 'seller_order_id_example'; // string | An order identifier that is specified by the seller. Used to select only the orders that match the order identifier. If SellerOrderId is specified, then FulfillmentChannels, OrderStatuses, PaymentMethod, LastUpdatedAfter, LastUpdatedBefore, and BuyerEmail cannot be specified.
$max_results_per_page = 56; // int | A number that indicates the maximum number of orders that can be returned per page. Value must be 1 - 100. Default 100.
$easy_ship_shipment_statuses = array('easy_ship_shipment_statuses_example'); // string[] | A list of EasyShipShipmentStatus values. Used to select Easy Ship orders with statuses that match the specified  values. If EasyShipShipmentStatus is specified, only Amazon Easy Ship orders are returned.Possible values: PendingPickUp (Amazon has not yet picked up the package from the seller). LabelCanceled (The seller canceled the pickup). PickedUp (Amazon has picked up the package from the seller). AtOriginFC (The packaged is at the origin fulfillment center). AtDestinationFC (The package is at the destination fulfillment center). OutForDelivery (The package is out for delivery). Damaged (The package was damaged by the carrier). Delivered (The package has been delivered to the buyer). RejectedByBuyer (The package has been rejected by the buyer). Undeliverable (The package cannot be delivered). ReturnedToSeller (The package was not delivered to the buyer and was returned to the seller). ReturningToSeller (The package was not delivered to the buyer and is being returned to the seller).
$next_token = 'next_token_example'; // string | A string token returned in the response of your previous request.
$amazon_order_ids = array('amazon_order_ids_example'); // string[] | A list of AmazonOrderId values. An AmazonOrderId is an Amazon-defined order identifier, in 3-7-7 format.

try {
    $result = $apiInstance->getOrders($marketplace_ids, $created_after, $created_before, $last_updated_after, $last_updated_before, $order_statuses, $fulfillment_channels, $payment_methods, $buyer_email, $seller_order_id, $max_results_per_page, $easy_ship_shipment_statuses, $next_token, $amazon_order_ids);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrdersApi->getOrders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **marketplace_ids** | [**string[]**](../Model/Orders/string.md)| A list of MarketplaceId values. Used to select orders that were placed in the specified marketplaces. |
 **created_after** | **string**| A date used for selecting orders created after (or at) a specified time. Only orders placed after the specified time are returned. Either the CreatedAfter parameter or the LastUpdatedAfter parameter is required. Both cannot be empty. The date must be in ISO 8601 format. | [optional]
 **created_before** | **string**| A date used for selecting orders created before (or at) a specified time. Only orders placed before the specified time are returned. The date must be in ISO 8601 format. | [optional]
 **last_updated_after** | **string**| A date used for selecting orders that were last updated after (or at) a specified time. An update is defined as any change in order status, including the creation of a new order. Includes updates made by Amazon and by the seller. The date must be in ISO 8601 format. | [optional]
 **last_updated_before** | **string**| A date used for selecting orders that were last updated before (or at) a specified time. An update is defined as any change in order status, including the creation of a new order. Includes updates made by Amazon and by the seller. The date must be in ISO 8601 format. | [optional]
 **order_statuses** | [**string[]**](../Model/Orders/string.md)| A list of OrderStatus values used to filter the results. Possible values: PendingAvailability (This status is available for pre-orders only. The order has been placed, payment has not been authorized, and the release date of the item is in the future.); Pending (The order has been placed but payment has not been authorized); Unshipped (Payment has been authorized and the order is ready for shipment, but no items in the order have been shipped); PartiallyShipped (One or more, but not all, items in the order have been shipped); Shipped (All items in the order have been shipped); InvoiceUnconfirmed (All items in the order have been shipped. The seller has not yet given confirmation to Amazon that the invoice has been shipped to the buyer.); Canceled (The order has been canceled); and Unfulfillable (The order cannot be fulfilled. This state applies only to Multi-Channel Fulfillment orders.). | [optional]
 **fulfillment_channels** | [**string[]**](../Model/Orders/string.md)| A list that indicates how an order was fulfilled. Filters the results by fulfillment channel. Possible values: FBA (Fulfillment by Amazon); SellerFulfilled (Fulfilled by the seller). | [optional]
 **payment_methods** | [**string[]**](../Model/Orders/string.md)| A list of payment method values. Used to select orders paid using the specified payment methods. Possible values: COD (Cash on delivery); CVS (Convenience store payment); Other (Any payment method other than COD or CVS). | [optional]
 **buyer_email** | **string**| The email address of a buyer. Used to select orders that contain the specified email address. | [optional]
 **seller_order_id** | **string**| An order identifier that is specified by the seller. Used to select only the orders that match the order identifier. If SellerOrderId is specified, then FulfillmentChannels, OrderStatuses, PaymentMethod, LastUpdatedAfter, LastUpdatedBefore, and BuyerEmail cannot be specified. | [optional]
 **max_results_per_page** | **int**| A number that indicates the maximum number of orders that can be returned per page. Value must be 1 - 100. Default 100. | [optional]
 **easy_ship_shipment_statuses** | [**string[]**](../Model/Orders/string.md)| A list of EasyShipShipmentStatus values. Used to select Easy Ship orders with statuses that match the specified  values. If EasyShipShipmentStatus is specified, only Amazon Easy Ship orders are returned.Possible values: PendingPickUp (Amazon has not yet picked up the package from the seller). LabelCanceled (The seller canceled the pickup). PickedUp (Amazon has picked up the package from the seller). AtOriginFC (The packaged is at the origin fulfillment center). AtDestinationFC (The package is at the destination fulfillment center). OutForDelivery (The package is out for delivery). Damaged (The package was damaged by the carrier). Delivered (The package has been delivered to the buyer). RejectedByBuyer (The package has been rejected by the buyer). Undeliverable (The package cannot be delivered). ReturnedToSeller (The package was not delivered to the buyer and was returned to the seller). ReturningToSeller (The package was not delivered to the buyer and is being returned to the seller). | [optional]
 **next_token** | **string**| A string token returned in the response of your previous request. | [optional]
 **amazon_order_ids** | [**string[]**](../Model/Orders/string.md)| A list of AmazonOrderId values. An AmazonOrderId is an Amazon-defined order identifier, in 3-7-7 format. | [optional]

### Return type

[**\SellingPartnerApi\Model\Orders\GetOrdersResponse**](../Model/Orders/GetOrdersResponse.md)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Top]](#) [[API list]](../)
[[Orders Model list]](../Model/Orders)
[[README]](../../README.md)
