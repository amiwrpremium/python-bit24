# Quick Start

Here are some snippets to get you started.

## Initiate

Initiate client.


??? code-ref "Reference"

    - Code Reference: [Client](../reference/clients)

=== "Sync"

    ```python title="client.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")
    ```

=== "Async"

    ```python title="client.py" linenums="1"
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")
    ```

### With Request Params

You can pass [requests](https://docs.python-requests.org/en/master/) OR [aiohttp](https://docs.aiohttp.org/en/stable/) params to client.

=== "Sync"

    ``` python title="with_request_params.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>", requests_params={
        "timeout": 10
    })
    ```

=== "Async"

    ``` python title="async_with_request_params.py" linenums="1"
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>", requests_params={
        "timeout": 10
    })
    ```

## Get Withdraw Networks

Get Withdraw Networks

!!! warning
    :material-car-speed-limiter:{ .rateLimit } Rate Limit: 120/minute


??? code-ref "Reference"

    - Sync Code Reference: [Client.get_withdraw_networks](../reference/clients#src.bit24.clients.Client.get_withdraw_networks)
    - Async Code Reference: [AsyncClient.get_withdraw_networks](../reference/clients#src.bit24.clients.AsyncClient.get_withdraw_networks)
    - API Documentation Reference: [Get Withdraw Networks](https://docs.bit24.cash/#adbd1760ac)

=== "Sync"

    ```python title="get_withdraw_networks.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_withdraw_networks()
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_withdraw_networks_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.get_withdraw_networks()
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "data": {
    "balance": "0",
    "networks": [
      {
        "network_id": 703,
        "network_name": "BTC",
        "network_layer": "BTC",
        "min_withdraw": "0.001",
        "max_withdraw": "500",
        "fee": "0.00022",
        "address_regex": "^[13][a-km-zA-HJ-NP-Z1-9]{25,34}$|^[(bc1q)|(bc1p)][0-9A-Za-z]{37,62}$",
        "memo_regex": null
      }
    ],
    "message": ""
  },
  "error": null
}
```

## Get Deposit Networks

Get Deposit Networks

??? code-ref "Reference"

    - Sync Code Reference: [Client.get_deposit_networks](../reference/clients#src.bit24.clients.Client.get_deposit_networks)
    - Async Code Reference: [AsyncClient.get_deposit_networks](../reference/clients#src.bit24.clients.AsyncClient.get_deposit_networks)
    - API Documentation Reference: [Get Deposit Networks](https://docs.bit24.cash/#adbd1760ac)

=== "Sync"

    ```python title="get_deposit_networks.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_deposit_networks()
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_deposit_networks_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        user_info = await client.get_deposit_networks()
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "data": {
    "networks": [
      {
        "network_name": "BTC",
        "network_layer": "BTC",
        "description_deposit": null,
        "min_deposit": "0.0005",
        "address": "1B9Y7E5nnYrW7JR6xxXrTVRDN1vDDLjvNM",
        "memo": null
      }
    ],
    "message": ""
  },
  "error": null
}
```

## Get Asset Information

Get Deposit Networks

??? code-ref "Reference"

    - Sync Code Reference: [Client.get_assets_information](../reference/clients#src.bit24.clients.Client.get_assets_information)
    - Async Code Reference: [AsyncClient.get_assets_information](../reference/clients#src.bit24.clients.AsyncClient.get_assets_information)
    - API Documentation Reference: [Get Deposit Networks](https://docs.bit24.cash/#3b0091253d)

=== "Sync"

    ```python title="get_assets_information.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_assets_information("bitcoin")
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_assets_information_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.get_assets_information()
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "",
    "asset": [
      {
        "id": 1,
        "name": "bitcoin",
        "fa_name": "بیت کوین",
        "symbol": "BTC",
        "coin_type": 0,
        "web_icon": "https://storage.bit24.exchange/exchange/icons/ca4e6136-b7e0-407d-81d6-fdf21910cc53.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/ca4e6136-b7e0-407d-81d6-fdf21910cc53.png",
        "each_price": "63495.9000000000000000",
        "change_24hr": "0.00",
        "balance": null,
        "available_balance": null,
        "in_orders": null,
        "balance_irt": "0",
        "balance_usdt": "0.00",
        "markets": [
          {
            "base_coin_symbol": "BTC",
            "quote_coin_symbol": "IRT",
            "is_active": 1
          },
          {
            "base_coin_symbol": "BTC",
            "quote_coin_symbol": "USDT",
            "is_active": 1
          }
        ]
      },
      {
        "id": 5,
        "name": "Bitcoin Cash",
        "fa_name": "بیت کوین کش",
        "symbol": "BCH",
        "coin_type": 0,
        "web_icon": "https://storage.bit24.exchange/exchange/icons/8742adc8-9dc6-4611-9167-09652f10ae2a.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/8742adc8-9dc6-4611-9167-09652f10ae2a.png",
        "each_price": "469.6600000000000000",
        "change_24hr": "6.61",
        "balance": null,
        "available_balance": null,
        "in_orders": null,
        "balance_irt": "0",
        "balance_usdt": "0.00",
        "markets": []
      },
      {
        "id": 278,
        "name": "Bitcoin Gold",
        "fa_name": "بیت کوین گلد",
        "symbol": "BTG",
        "coin_type": 0,
        "web_icon": "https://storage.bit24.exchange/exchange/icons/e9c508b8-076f-422d-b754-b7fce5f4fefc.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/e9c508b8-076f-422d-b754-b7fce5f4fefc.png",
        "each_price": "0.0000000000000000",
        "change_24hr": "0.00",
        "balance": null,
        "available_balance": null,
        "in_orders": null,
        "balance_irt": "0",
        "balance_usdt": "0.00",
        "markets": []
      },
      {
        "id": 299,
        "name": "Bitcoin Standard Hashrate Token",
        "fa_name": "بیتکوین استاندارد",
        "symbol": "BTCST",
        "coin_type": 0,
        "web_icon": "https://storage.bit24.exchange/exchange/icons/50aa595e-e601-4d42-bca0-ef293c08a778.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/50aa595e-e601-4d42-bca0-ef293c08a778.png",
        "each_price": "0.0000000000000000",
        "change_24hr": "0.00",
        "balance": null,
        "available_balance": null,
        "in_orders": null,
        "balance_irt": "0",
        "balance_usdt": "0.00",
        "markets": []
      },
      {
        "id": 434,
        "name": "Super Bitcoin",
        "fa_name": "سوپر بیت کوین",
        "symbol": "SBTC",
        "coin_type": 0,
        "web_icon": "https://storage.bit24.exchange/exchange/icons/SBTC.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/SBTC.png",
        "each_price": "0.3897000000000000",
        "change_24hr": "-3.46",
        "balance": null,
        "available_balance": null,
        "in_orders": null,
        "balance_irt": "0",
        "balance_usdt": "0.00",
        "markets": []
      }
    ]
  }
}
```

## Get Asset History

Get Deposit History

??? code-ref "Reference"

    - Sync Code Reference: [Client.get_assets_information](../reference/clients#src.bit24.clients.Client.get_assets_history)
    - Async Code Reference: [AsyncClient.get_assets_information](../reference/clients#src.bit24.clients.AsyncClient.get_assets_history)
    - API Documentation Reference: [Get Asset History](https://docs.bit24.cash/#84b216ea06)

=== "Sync"

    ```python title="get_assets_history.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_assets_history("bitcoin")
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_assets_history_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient


    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.get_assets_history()
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "",
    "has_paginate": 1,
    "total_data": 2,
    "current_page": 1,
    "from": 1,
    "to": 2,
    "per_page": 40,
    "results": [
      {
        "id": 8920202,
        "name": "Toman",
        "fa_name": "تومان",
        "symbol": "IRT",
        "logo": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "value": "166800.00000000",
        "done_value": "0.00000000",
        "type": 0,
        "transaction_code": "6W663612dbb4fbaas",
        "type_text": "کاهشی",
        "reason_type": "2",
        "reason_text": null,
        "reason_type_text": "معامله حرفه‌ای",
        "reason_id": 366287355,
        "balance_status": 0,
        "balance_status_text": "در حال انجام",
        "commission": 0,
        "final_commission": "0",
        "created_at": "2024-05-04 14:20:03",
        "created_at_jalali": "1403/2/15 14:20:03"
      },
      {
        "id": 8918154,
        "name": "Toman",
        "fa_name": "تومان",
        "symbol": "IRT",
        "logo": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "value": "500000.00000000",
        "done_value": "500000.00000000",
        "type": 1,
        "transaction_code": "VL6635f357c6bfbK4",
        "type_text": " افزایشی",
        "reason_type": "0",
        "reason_text": "شارژ کیف پول از درگاه بانکی",
        "reason_type_text": "واریز",
        "reason_id": 787573,
        "balance_status": 1,
        "balance_status_text": "تکمیل شده",
        "commission": 0,
        "final_commission": "0",
        "created_at": "2024-05-04 12:05:35",
        "created_at_jalali": "1403/2/15 12:05:35"
      }
    ]
  }
}
```

## Create Order

Create Order

??? code-ref "Reference"

    - Sync Code Reference: [Client.create_order](../reference/clients#src.bit24.clients.Client.create_order)
    - Async Code Reference: [AsyncClient.create_order](../reference/clients#src.bit24.clients.AsyncClient.create_order)
    - API Documentation Reference: [Create Order](https://docs.bit24.cash/#34b353d77b)

=== "Sync"

    ```python title="create_order.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.create_order(
            base_coin_symbol="USDT",
            quote_coin_symbol="IRT",
            category_type="0",
            type="1",
            amount=2,
            price=60_000,
        )
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="create_order_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.create_order(
            base_coin_symbol="USDT",
            quote_coin_symbol="IRT",
            category_type="0",
            type="1",
            amount=2,
            price=60_000,
        )
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "سفارش با موفقیت ثبت شد",
    "order": {
      "id": 366365493,
      "type": 1,
      "each_price": "60000",
      "stop_price": "0",
      "trigger_price": "0",
      "amount": "2.0",
      "available_amount": "2",
      "done_value": "0.0",
      "done_percent": "0.00",
      "mean_value": 0,
      "commission": null,
      "total": "120000",
      "created_at": "2024-05-04 15:43:07",
      "created_at_jalali": "1403/2/15 15:43:07",
      "base_coin": {
        "id": 6,
        "symbol": "USDT",
        "name": "Tether",
        "fa_name": "تتر",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
      },
      "quote_coin": {
        "id": 524,
        "symbol": "IRT",
        "name": "Toman",
        "fa_name": "تومان",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
      },
      "status": 0,
      "status_text": "در حال تکمیل",
      "category_type": "0",
      "category_type_text": "عادی",
      "club_commission_discount_amount": null,
      "conditions": "-",
      "triggered_category_type": null,
      "is_trade": 0,
      "trailing_price_condition": "",
      "activation_price_condition": "",
      "delta": "% "
    }
  }
}
```

## Cancel Order

Cancel Order

??? code-ref "Reference"

    - Sync Code Reference: [Client.cancel_order](../reference/clients#src.bit24.clients.Client.cancel_order)
    - Async Code Reference: [AsyncClient.cancel_order](../reference/clients#src.bit24.clients.AsyncClient.cancel_order)
    - API Documentation Reference: [Cancel Order](https://docs.bit24.cash/#27f17a67f7)

=== "Sync"

    ```python title="cancel_order.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.cancel_order(
            order_id=366375085,
        )
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="cancel_order_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.cancel_order(
            order_id=366375085
        )
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "لغو سفارش/سفارشات با موفقیت انجام شد."
  }
}
```

## Get Order/Trade History

Get Orders and Trades History

??? code-ref "Reference"

    - Sync Code Reference: [Client.get_orders_history](../reference/clients#src.bit24.clients.Client.get_orders_history)
    - Async Code Reference: [AsyncClient.get_orders_history](../reference/clients#src.bit24.clients.AsyncClient.get_orders_history)
    - API Documentation Reference: [Get Order History](https://docs.bit24.cash/#f80b280d82)

=== "Sync"

    ```python title="get_orders_history.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_orders_history("0")
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_orders_history_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.get_orders_history("0")
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "",
    "has_paginate": 1,
    "total_data": 6,
    "current_page": 1,
    "from": 1,
    "to": 6,
    "per_page": 40,
    "results": [
      {
        "id": 366382815,
        "type": 1,
        "each_price": "60000",
        "stop_price": "0",
        "trigger_price": "0",
        "amount": "2.0",
        "available_amount": "2.00000000",
        "done_value": "0.0",
        "done_percent": "0.00",
        "mean_value": "0.0000000000000000",
        "commission": "0.0",
        "total": "120000",
        "created_at": "2024-05-04 16:08:20",
        "created_at_jalali": "1403/2/15 16:08:20",
        "base_coin": {
          "id": 6,
          "symbol": "USDT",
          "name": "Tether",
          "fa_name": "تتر",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
        },
        "quote_coin": {
          "id": 524,
          "symbol": "IRT",
          "name": "Toman",
          "fa_name": "تومان",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
        },
        "status": 2,
        "status_text": "لغو شده",
        "category_type": 0,
        "category_type_text": "عادی",
        "club_commission_discount_amount": "0.000000000000",
        "conditions": "-",
        "triggered_category_type": null,
        "is_trade": 0,
        "trailing_price_condition": "",
        "activation_price_condition": "",
        "delta": "% "
      },
      {
        "id": 366375085,
        "type": 1,
        "each_price": "60000",
        "stop_price": "0",
        "trigger_price": "0",
        "amount": "2.0",
        "available_amount": "2.00000000",
        "done_value": "0.0",
        "done_percent": "0.00",
        "mean_value": "0.0000000000000000",
        "commission": "0.0",
        "total": "120000",
        "created_at": "2024-05-04 15:57:14",
        "created_at_jalali": "1403/2/15 15:57:14",
        "base_coin": {
          "id": 6,
          "symbol": "USDT",
          "name": "Tether",
          "fa_name": "تتر",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
        },
        "quote_coin": {
          "id": 524,
          "symbol": "IRT",
          "name": "Toman",
          "fa_name": "تومان",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
        },
        "status": 2,
        "status_text": "لغو شده",
        "category_type": 0,
        "category_type_text": "عادی",
        "club_commission_discount_amount": "0.000000000000",
        "conditions": "-",
        "triggered_category_type": null,
        "is_trade": 0,
        "trailing_price_condition": "",
        "activation_price_condition": "",
        "delta": "% "
      },
      {
        "id": 366365493,
        "type": 1,
        "each_price": "60000",
        "stop_price": "0",
        "trigger_price": "0",
        "amount": "2.0",
        "available_amount": "2.00000000",
        "done_value": "0.0",
        "done_percent": "0.00",
        "mean_value": "0.0000000000000000",
        "commission": "0.0",
        "total": "120000",
        "created_at": "2024-05-04 15:43:07",
        "created_at_jalali": "1403/2/15 15:43:07",
        "base_coin": {
          "id": 6,
          "symbol": "USDT",
          "name": "Tether",
          "fa_name": "تتر",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
        },
        "quote_coin": {
          "id": 524,
          "symbol": "IRT",
          "name": "Toman",
          "fa_name": "تومان",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
        },
        "status": 2,
        "status_text": "لغو شده",
        "category_type": 0,
        "category_type_text": "عادی",
        "club_commission_discount_amount": "0.000000000000",
        "conditions": "-",
        "triggered_category_type": null,
        "is_trade": 0,
        "trailing_price_condition": "",
        "activation_price_condition": "",
        "delta": "% "
      },
      {
        "id": 366356907,
        "type": 1,
        "each_price": "60000",
        "stop_price": "0",
        "trigger_price": "0",
        "amount": "2.0",
        "available_amount": "2.00000000",
        "done_value": "0.0",
        "done_percent": "0.00",
        "mean_value": "0.0000000000000000",
        "commission": "0.0",
        "total": "120000",
        "created_at": "2024-05-04 15:32:54",
        "created_at_jalali": "1403/2/15 15:32:54",
        "base_coin": {
          "id": 6,
          "symbol": "USDT",
          "name": "Tether",
          "fa_name": "تتر",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
        },
        "quote_coin": {
          "id": 524,
          "symbol": "IRT",
          "name": "Toman",
          "fa_name": "تومان",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
        },
        "status": 2,
        "status_text": "لغو شده",
        "category_type": 0,
        "category_type_text": "عادی",
        "club_commission_discount_amount": "0.000000000000",
        "conditions": "-",
        "triggered_category_type": null,
        "is_trade": 0,
        "trailing_price_condition": "",
        "activation_price_condition": "",
        "delta": "% "
      },
      {
        "id": 366287355,
        "type": 1,
        "each_price": "55600",
        "stop_price": "0",
        "trigger_price": "0",
        "amount": "3.0",
        "available_amount": "3.00000000",
        "done_value": "0.0",
        "done_percent": "0.00",
        "mean_value": "0.0000000000000000",
        "commission": "0.0",
        "total": "166800",
        "created_at": "2024-05-04 14:20:03",
        "created_at_jalali": "1403/2/15 14:20:03",
        "base_coin": {
          "id": 6,
          "symbol": "USDT",
          "name": "Tether",
          "fa_name": "تتر",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
        },
        "quote_coin": {
          "id": 524,
          "symbol": "IRT",
          "name": "Toman",
          "fa_name": "تومان",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
        },
        "status": 0,
        "status_text": "در حال تکمیل",
        "category_type": 0,
        "category_type_text": "عادی",
        "club_commission_discount_amount": "0.000000000000",
        "conditions": "-",
        "triggered_category_type": null,
        "is_trade": 0,
        "trailing_price_condition": "",
        "activation_price_condition": "",
        "delta": "% "
      },
      {
        "id": 366270795,
        "type": 1,
        "each_price": "61200",
        "stop_price": "0",
        "trigger_price": "0",
        "amount": "3.0",
        "available_amount": "3.00000000",
        "done_value": "0.0",
        "done_percent": "0.00",
        "mean_value": "0.0000000000000000",
        "commission": "0.0",
        "total": "183600",
        "created_at": "2024-05-04 14:01:16",
        "created_at_jalali": "1403/2/15 14:01:16",
        "base_coin": {
          "id": 6,
          "symbol": "USDT",
          "name": "Tether",
          "fa_name": "تتر",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png"
        },
        "quote_coin": {
          "id": 524,
          "symbol": "IRT",
          "name": "Toman",
          "fa_name": "تومان",
          "web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
          "app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png"
        },
        "status": 2,
        "status_text": "لغو شده",
        "category_type": 0,
        "category_type_text": "عادی",
        "club_commission_discount_amount": "0.000000000000",
        "conditions": "-",
        "triggered_category_type": null,
        "is_trade": 0,
        "trailing_price_condition": "",
        "activation_price_condition": "",
        "delta": "% "
      }
    ]
  }
}
```

## Get Markets Information

Get Markets Information

??? code-ref "Reference"

    - Sync Code Reference: [Client.get_markets_information](../reference/clients#src.bit24.clients.Client.get_markets_information)
    - Async Code Reference: [AsyncClient.get_markets_information](../reference/clients#src.bit24.clients.AsyncClient.get_markets_information)
    - API Documentation Reference: [Get Markets Information](https://docs.bit24.cash/#52dd1f3149)

=== "Sync"

    ```python title="get_markets_information.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_markets_information(
            order_id=366375085,
        )
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_markets_information_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.get_markets_information()
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "",
    "has_paginate": 1,
    "total_data": 295,
    "current_page": 1,
    "from": 1,
    "to": 40,
    "per_page": 40,
    "results": [
      {
        "id": 7,
        "base_coin_id": 6,
        "base_coin_name": "Tether",
        "base_coin_fa_name": "تتر",
        "base_coin_symbol": "USDT",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "61281",
        "other_side_each_price": null,
        "quote_coin_volume": "27677820011",
        "base_coin_volume": "451654.1",
        "24h_change": "-0.703",
        "24h_change_volume": "-434",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "1.7",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/596ac4ed-3c63-45cf-9f30-c28646ec0532.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "61715",
        "last_order": "61281",
        "min_price": "61193",
        "max_price": "62008",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-usdtirt.png",
        "is_favorite": false
      },
      {
        "id": 499,
        "base_coin_id": 629,
        "base_coin_name": "dogwifhat",
        "base_coin_fa_name": "ویف",
        "base_coin_symbol": "WIF",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "208990",
        "other_side_each_price": null,
        "quote_coin_volume": "26451502170",
        "base_coin_volume": "126568.26",
        "24h_change": "18.744",
        "24h_change_volume": "32990",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.48",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/WIF.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/WIF.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "176000",
        "last_order": "208990",
        "min_price": "176000",
        "max_price": "212236",
        "base_coin_decimal": 2,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-wifirt.png",
        "is_favorite": false
      },
      {
        "id": 21,
        "base_coin_id": 172,
        "base_coin_name": "SHIBA INU",
        "base_coin_fa_name": "شیبا اینو",
        "base_coin_symbol": "SHIB",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "1.500",
        "other_side_each_price": null,
        "quote_coin_volume": "23156408917",
        "base_coin_volume": "15437605945",
        "24h_change": "3.021",
        "24h_change_volume": "0.044",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.000",
        "market_order_base_coin_total_min": "66667",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/db261fcb-31e8-4034-a4ff-82cbf18f05e8.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/db261fcb-31e8-4034-a4ff-82cbf18f05e8.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "1.456",
        "last_order": "1.500",
        "min_price": "1.449",
        "max_price": "1.553",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 3,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-shibirt.png",
        "is_favorite": false
      },
      {
        "id": 19,
        "base_coin_id": 20,
        "base_coin_name": "Dogecoin",
        "base_coin_fa_name": "دوج کوین",
        "base_coin_symbol": "DOGE",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "9822",
        "other_side_each_price": null,
        "quote_coin_volume": "9075576158",
        "base_coin_volume": "924004",
        "24h_change": "15.921",
        "24h_change_volume": "1349",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "11",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/c9718cb5-4651-45a1-850a-91000fc82b25.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/c9718cb5-4651-45a1-850a-91000fc82b25.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "8473",
        "last_order": "9822",
        "min_price": "8436",
        "max_price": "9918",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-dogeirt.png",
        "is_favorite": false
      },
      {
        "id": 313,
        "base_coin_id": 441,
        "base_coin_name": "Pepe",
        "base_coin_fa_name": "پپه",
        "base_coin_symbol": "PEPE",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "0.5394",
        "other_side_each_price": null,
        "quote_coin_volume": "7926476314",
        "base_coin_volume": "14694987606",
        "24h_change": "10.081",
        "24h_change_volume": "0.0494",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.0000",
        "market_order_base_coin_total_min": "185392",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/PEPE.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/PEPE.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "0.4900",
        "last_order": "0.5394",
        "min_price": "0.4797",
        "max_price": "0.5400",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 4,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-pepeirt.png",
        "is_favorite": false
      },
      {
        "id": 1,
        "base_coin_id": 1,
        "base_coin_name": "bitcoin",
        "base_coin_fa_name": "بیت کوین",
        "base_coin_symbol": "BTC",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "3918338910",
        "other_side_each_price": null,
        "quote_coin_volume": "5834440922",
        "base_coin_volume": "1.489008",
        "24h_change": "4.712",
        "24h_change_volume": "176344970",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.000026",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/ca4e6136-b7e0-407d-81d6-fdf21910cc53.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/ca4e6136-b7e0-407d-81d6-fdf21910cc53.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "3741993940",
        "last_order": "3918338910",
        "min_price": "3727007010",
        "max_price": "3962814000",
        "base_coin_decimal": 6,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-btcirt.png",
        "is_favorite": false
      },
      {
        "id": 497,
        "base_coin_id": 630,
        "base_coin_name": "Wen",
        "base_coin_fa_name": "ون",
        "base_coin_symbol": "WEN",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "13.12",
        "other_side_each_price": null,
        "quote_coin_volume": "4849549437",
        "base_coin_volume": "369630292",
        "24h_change": "1.942",
        "24h_change_volume": "0.25",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.00",
        "market_order_base_coin_total_min": "7622",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/WEN.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/WEN.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "12.87",
        "last_order": "13.12",
        "min_price": "12.26",
        "max_price": "13.47",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 2,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-wenirt.png",
        "is_favorite": false
      },
      {
        "id": 307,
        "base_coin_id": 404,
        "base_coin_name": "Toncoin",
        "base_coin_fa_name": "تن کوین",
        "base_coin_symbol": "TON",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "351788",
        "other_side_each_price": null,
        "quote_coin_volume": "4791427568",
        "base_coin_volume": "13620.21",
        "24h_change": "5.590",
        "24h_change_volume": "18627",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.29",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/ton11122.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/ton11122.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "333161",
        "last_order": "351788",
        "min_price": "333161",
        "max_price": "359013",
        "base_coin_decimal": 2,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-tonirt.png",
        "is_favorite": false
      },
      {
        "id": 265,
        "base_coin_id": 321,
        "base_coin_name": "Floki Inu",
        "base_coin_fa_name": "فلوکی اینو",
        "base_coin_symbol": "FLOKI",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "12.32",
        "other_side_each_price": null,
        "quote_coin_volume": "4545605082",
        "base_coin_volume": "368961451",
        "24h_change": "20.547",
        "24h_change_volume": "2.10",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.00",
        "market_order_base_coin_total_min": "8117",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/32879dd0-cb5a-49ec-b08f-4ee525a2d14e.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/32879dd0-cb5a-49ec-b08f-4ee525a2d14e.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "10.22",
        "last_order": "12.32",
        "min_price": "10.22",
        "max_price": "12.50",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 2,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-flokiirt.png",
        "is_favorite": false
      },
      {
        "id": 306,
        "base_coin_id": 480,
        "base_coin_name": "SpaceFalcon",
        "base_coin_fa_name": "اسپیس فالکون",
        "base_coin_symbol": "FCON",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "42.62",
        "other_side_each_price": null,
        "quote_coin_volume": "2784542491",
        "base_coin_volume": "65334173",
        "24h_change": "7.953",
        "24h_change_volume": "3.14",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.00",
        "market_order_base_coin_total_min": "2347",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/FCON.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/FCON.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "39.48",
        "last_order": "42.62",
        "min_price": "37.50",
        "max_price": "47.91",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 2,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-fconirt.png",
        "is_favorite": false
      },
      {
        "id": 481,
        "base_coin_id": 67,
        "base_coin_name": "Solana",
        "base_coin_fa_name": "سولانا",
        "base_coin_symbol": "SOL",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "9046715",
        "other_side_each_price": null,
        "quote_coin_volume": "2489570311",
        "base_coin_volume": "275.190",
        "24h_change": "3.381",
        "24h_change_volume": "295928",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.012",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/eb1e607f-998e-4d5e-b006-a78fdcce9ec3.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/eb1e607f-998e-4d5e-b006-a78fdcce9ec3.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "8750787",
        "last_order": "9046715",
        "min_price": "8648437",
        "max_price": "9240785",
        "base_coin_decimal": 3,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-solirt.png",
        "is_favorite": false
      },
      {
        "id": 491,
        "base_coin_id": 620,
        "base_coin_name": "Myro",
        "base_coin_fa_name": "مایرو",
        "base_coin_symbol": "MYRO",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "10695",
        "other_side_each_price": null,
        "quote_coin_volume": "1726320491",
        "base_coin_volume": "161413.7",
        "24h_change": "15.061",
        "24h_change_volume": "1400",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "9.4",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/MYRO.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/MYRO.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "9295",
        "last_order": "10695",
        "min_price": "9211",
        "max_price": "10993",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-myroirt.png",
        "is_favorite": false
      },
      {
        "id": 258,
        "base_coin_id": 466,
        "base_coin_name": "Milady Meme Coin",
        "base_coin_fa_name": "لیدیز",
        "base_coin_symbol": "LADYS",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "0.01087",
        "other_side_each_price": null,
        "quote_coin_volume": "1660538753",
        "base_coin_volume": "152763454799",
        "24h_change": "10.042",
        "24h_change_volume": "0.00099",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.00000",
        "market_order_base_coin_total_min": "9199633",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/LADYS1.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/LADYS1.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "0.00987",
        "last_order": "0.01087",
        "min_price": "0.00972",
        "max_price": "0.01104",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 5,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-ladysirt.png",
        "is_favorite": false
      },
      {
        "id": 487,
        "base_coin_id": 389,
        "base_coin_name": "Bonk",
        "base_coin_fa_name": "بنک",
        "base_coin_symbol": "BONK",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "1.754",
        "other_side_each_price": null,
        "quote_coin_volume": "1581261005",
        "base_coin_volume": "901517106",
        "24h_change": "3.358",
        "24h_change_volume": "0.057",
        "total_min": "660000.00000000",
        "market_order_quote_coin_total_min": "660000.000",
        "market_order_base_coin_total_min": "376283",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/e3df71df-ea0c-4ed6-b968-cb3b6cf43d38.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/e3df71df-ea0c-4ed6-b968-cb3b6cf43d38.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "1.697",
        "last_order": "1.754",
        "min_price": "1.619",
        "max_price": "1.800",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 3,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-bonkirt.png",
        "is_favorite": false
      },
      {
        "id": 18,
        "base_coin_id": 14,
        "base_coin_name": "Cardano",
        "base_coin_fa_name": "کاردانو",
        "base_coin_symbol": "ADA",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "28847",
        "other_side_each_price": null,
        "quote_coin_volume": "1288963998",
        "base_coin_volume": "44682.7",
        "24h_change": "1.930",
        "24h_change_volume": "546",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "3.5",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/179a5e93-2916-4f9f-b385-97b6aa8e7dfe.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/179a5e93-2916-4f9f-b385-97b6aa8e7dfe.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "28289",
        "last_order": "28835",
        "min_price": "28082",
        "max_price": "29293",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-adairt.png",
        "is_favorite": false
      },
      {
        "id": 9,
        "base_coin_id": 11,
        "base_coin_name": "Tron",
        "base_coin_fa_name": "ترون",
        "base_coin_symbol": "TRX",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "7552",
        "other_side_each_price": null,
        "quote_coin_volume": "1242373515",
        "base_coin_volume": "164509",
        "24h_change": "-0.079",
        "24h_change_volume": "-6",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "14",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/TRX.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/TRX.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "7558",
        "last_order": "7552",
        "min_price": "7489",
        "max_price": "7689",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-trxirt.png",
        "is_favorite": false
      },
      {
        "id": 274,
        "base_coin_id": 405,
        "base_coin_name": "Arbitrum",
        "base_coin_fa_name": "آربیتروم",
        "base_coin_symbol": "ARB",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "66020",
        "other_side_each_price": null,
        "quote_coin_volume": "1166794882",
        "base_coin_volume": "17673.3",
        "24h_change": "2.345",
        "24h_change_volume": "1513",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "1.6",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/4220e9ec-f912-491d-ba89-6cd85abcad68.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/4220e9ec-f912-491d-ba89-6cd85abcad68.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "64507",
        "last_order": "66020",
        "min_price": "64100",
        "max_price": "66709",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-arbirt.png",
        "is_favorite": false
      },
      {
        "id": 314,
        "base_coin_id": 534,
        "base_coin_name": "Pepe 2",
        "base_coin_fa_name": "پپه 2",
        "base_coin_symbol": "PEPE2",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "0.002911",
        "other_side_each_price": null,
        "quote_coin_volume": "1131869842",
        "base_coin_volume": "388825091812",
        "24h_change": "3.226",
        "24h_change_volume": "0.000091",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.000000",
        "market_order_base_coin_total_min": "34352457",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/PEPE2.0.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/PEPE2.0.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "0.002820",
        "last_order": "0.002911",
        "min_price": "0.002752",
        "max_price": "0.003033",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 6,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-pepe2irt.png",
        "is_favorite": false
      },
      {
        "id": 477,
        "base_coin_id": 257,
        "base_coin_name": "babydoge",
        "base_coin_fa_name": "بیبی دوج",
        "base_coin_symbol": "BABYDOGE",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "0.0001208",
        "other_side_each_price": null,
        "quote_coin_volume": "901964071",
        "base_coin_volume": "7466589993075",
        "24h_change": "2.896",
        "24h_change_volume": "0.0000034",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.0000000",
        "market_order_base_coin_total_min": "827814570",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/287754d0-921a-464e-a17f-75dc2bb31985.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/287754d0-921a-464e-a17f-75dc2bb31985.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "0.0001174",
        "last_order": "0.0001208",
        "min_price": "0.0001171",
        "max_price": "0.0001255",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 7,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-babydogeirt.png",
        "is_favorite": false
      },
      {
        "id": 3,
        "base_coin_id": 3,
        "base_coin_name": "Ethereum",
        "base_coin_fa_name": "اتریوم",
        "base_coin_symbol": "ETH",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "192808729",
        "other_side_each_price": null,
        "quote_coin_volume": "769842906",
        "base_coin_volume": "3.99278",
        "24h_change": "2.719",
        "24h_change_volume": "5104372",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.00052",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/9510ed7b-dc8d-47a3-98ae-8b5fe6adb8eb.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/9510ed7b-dc8d-47a3-98ae-8b5fe6adb8eb.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "187704357",
        "last_order": "192808729",
        "min_price": "186493803",
        "max_price": "194768655",
        "base_coin_decimal": 5,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-ethirt.png",
        "is_favorite": false
      },
      {
        "id": 32,
        "base_coin_id": 111,
        "base_coin_name": "PancakeSwap",
        "base_coin_fa_name": "پنکیک سواپ",
        "base_coin_symbol": "CAKE",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "166000",
        "other_side_each_price": null,
        "quote_coin_volume": "719617839",
        "base_coin_volume": "4335.04",
        "24h_change": "4.192",
        "24h_change_volume": "6689",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.61",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/a5690177-d24d-4984-8a8f-50ceda849b8a.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/a5690177-d24d-4984-8a8f-50ceda849b8a.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "159556",
        "last_order": "166245",
        "min_price": "159432",
        "max_price": "168641",
        "base_coin_decimal": 2,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-cakeirt.png",
        "is_favorite": false
      },
      {
        "id": 286,
        "base_coin_id": 379,
        "base_coin_name": "OpenDAO",
        "base_coin_fa_name": "اوپن دائو",
        "base_coin_symbol": "SOS",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "0.001748",
        "other_side_each_price": null,
        "quote_coin_volume": "688530034",
        "base_coin_volume": "393895900662",
        "24h_change": "12.051",
        "24h_change_volume": "0.000188",
        "total_min": "660000.00000000",
        "market_order_quote_coin_total_min": "660000.000000",
        "market_order_base_coin_total_min": "377574371",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/245398a5-7da7-4efb-823e-97b6a30ddba7.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/245398a5-7da7-4efb-823e-97b6a30ddba7.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "0.001560",
        "last_order": "0.001748",
        "min_price": "0.001560",
        "max_price": "0.001829",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 6,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-sosirt.png",
        "is_favorite": false
      },
      {
        "id": 20,
        "base_coin_id": 4,
        "base_coin_name": "Ripple",
        "base_coin_fa_name": "ریپل",
        "base_coin_symbol": "XRP",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "32869",
        "other_side_each_price": null,
        "quote_coin_volume": "563893499",
        "base_coin_volume": "17155.7",
        "24h_change": "1.988",
        "24h_change_volume": "641",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "3.1",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/ad5efb7b-e514-498e-b7e9-e9bd02137e79.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/ad5efb7b-e514-498e-b7e9-e9bd02137e79.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "32228",
        "last_order": "32869",
        "min_price": "32206",
        "max_price": "33015",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-xrpirt.png",
        "is_favorite": false
      },
      {
        "id": 25,
        "base_coin_id": 45,
        "base_coin_name": "Uniswap",
        "base_coin_fa_name": "یونی سوآپ",
        "base_coin_symbol": "UNI",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "464212",
        "other_side_each_price": null,
        "quote_coin_volume": "535329249",
        "base_coin_volume": "1153.19",
        "24h_change": "4.230",
        "24h_change_volume": "18843",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.22",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/75f8f05b-b5cb-4573-a997-5292a9fe2b80.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/75f8f05b-b5cb-4573-a997-5292a9fe2b80.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "445369",
        "last_order": "464212",
        "min_price": "442931",
        "max_price": "474472",
        "base_coin_decimal": 2,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-uniirt.png",
        "is_favorite": false
      },
      {
        "id": 289,
        "base_coin_id": 350,
        "base_coin_name": "Green Satoshi Token",
        "base_coin_fa_name": "جی اس تی",
        "base_coin_symbol": "GST",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "1942",
        "other_side_each_price": null,
        "quote_coin_volume": "446606630",
        "base_coin_volume": "229972",
        "24h_change": "2.210",
        "24h_change_volume": "42",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "52",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/6e1b17df-d336-4ada-9d05-bfbb965410c0.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/6e1b17df-d336-4ada-9d05-bfbb965410c0.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "1900",
        "last_order": "1942",
        "min_price": "1900",
        "max_price": "2011",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-gstirt.png",
        "is_favorite": false
      },
      {
        "id": 483,
        "base_coin_id": 62,
        "base_coin_name": "Fantom",
        "base_coin_fa_name": "فانتوم",
        "base_coin_symbol": "FTM",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "43096",
        "other_side_each_price": null,
        "quote_coin_volume": "420030828",
        "base_coin_volume": "9746.3",
        "24h_change": "1.831",
        "24h_change_volume": "775",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "2.4",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/1b310cd6-c884-4999-8bbc-49f4dbc6415c.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/1b310cd6-c884-4999-8bbc-49f4dbc6415c.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "42321",
        "last_order": "43096",
        "min_price": "42036",
        "max_price": "43903",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-ftmirt.png",
        "is_favorite": false
      },
      {
        "id": 288,
        "base_coin_id": 450,
        "base_coin_name": "Sui",
        "base_coin_fa_name": "سویی",
        "base_coin_symbol": "SUI",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "67675",
        "other_side_each_price": null,
        "quote_coin_volume": "415267534",
        "base_coin_volume": "6136.2",
        "24h_change": "-0.649",
        "24h_change_volume": "-442",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "1.5",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/SUI.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/SUI.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "68055",
        "last_order": "67613",
        "min_price": "67501",
        "max_price": "70338",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-suiirt.png",
        "is_favorite": false
      },
      {
        "id": 226,
        "base_coin_id": 354,
        "base_coin_name": "JasmyCoin",
        "base_coin_fa_name": "جسمی کوین",
        "base_coin_symbol": "JASMY",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "1161",
        "other_side_each_price": null,
        "quote_coin_volume": "388906805",
        "base_coin_volume": "334975",
        "24h_change": "6.416",
        "24h_change_volume": "70",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "87",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/da8d91c4-de73-4d1c-b170-b464d7d013e9.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/da8d91c4-de73-4d1c-b170-b464d7d013e9.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "1091",
        "last_order": "1161",
        "min_price": "1082",
        "max_price": "1168",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-jasmyirt.png",
        "is_favorite": false
      },
      {
        "id": 325,
        "base_coin_id": 363,
        "base_coin_name": "Optimism",
        "base_coin_fa_name": "آپتیمیزم",
        "base_coin_symbol": "OP",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "179609",
        "other_side_each_price": null,
        "quote_coin_volume": "383720525",
        "base_coin_volume": "2136.42",
        "24h_change": "0.414",
        "24h_change_volume": "741",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.56",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/176388e7-7656-4a9f-890e-3b7e2d12dbb0.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/176388e7-7656-4a9f-890e-3b7e2d12dbb0.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "178868",
        "last_order": "179609",
        "min_price": "173438",
        "max_price": "184108",
        "base_coin_decimal": 2,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-opirt.png",
        "is_favorite": false
      },
      {
        "id": 176,
        "base_coin_id": 27,
        "base_coin_name": "Algorand",
        "base_coin_fa_name": "آلگوراند",
        "base_coin_symbol": "ALGO",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "11861",
        "other_side_each_price": null,
        "quote_coin_volume": "371211693",
        "base_coin_volume": "31296.8",
        "24h_change": "3.192",
        "24h_change_volume": "367",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "8.5",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/ee17b4a3-2aba-48b1-8f28-9f6941cfadf9.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/ee17b4a3-2aba-48b1-8f28-9f6941cfadf9.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "11494",
        "last_order": "11861",
        "min_price": "11426",
        "max_price": "11982",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-algoirt.png",
        "is_favorite": false
      },
      {
        "id": 273,
        "base_coin_id": 494,
        "base_coin_name": "Orbofi AI",
        "base_coin_fa_name": "اوبی",
        "base_coin_symbol": "OBI",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "1305",
        "other_side_each_price": null,
        "quote_coin_volume": "348250244",
        "base_coin_volume": "266858",
        "24h_change": "21.529",
        "24h_change_volume": "228",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "77",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/OBI.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/OBI.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "1059",
        "last_order": "1287",
        "min_price": "1048",
        "max_price": "1483",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-obiirt.png",
        "is_favorite": false
      },
      {
        "id": 17,
        "base_coin_id": 7,
        "base_coin_name": "Binance Coin",
        "base_coin_fa_name": "بایننس کوین",
        "base_coin_symbol": "BNB",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "36227441",
        "other_side_each_price": null,
        "quote_coin_volume": "332163953",
        "base_coin_volume": "9.1688",
        "24h_change": "2.902",
        "24h_change_volume": "1021730",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.0028",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/8cdfc019-7c47-49ad-b031-40c36017d810.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/8cdfc019-7c47-49ad-b031-40c36017d810.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "35205711",
        "last_order": "36227441",
        "min_price": "34984397",
        "max_price": "36494100",
        "base_coin_decimal": 4,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-bnbirt.png",
        "is_favorite": false
      },
      {
        "id": 305,
        "base_coin_id": 136,
        "base_coin_name": "Akropolis",
        "base_coin_fa_name": "آکرو پلیس",
        "base_coin_symbol": "AKRO",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "435.3",
        "other_side_each_price": null,
        "quote_coin_volume": "328616248",
        "base_coin_volume": "754919",
        "24h_change": "1.610",
        "24h_change_volume": "6.9",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.0",
        "market_order_base_coin_total_min": "230",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/b922c8b1-9a06-4a9a-a1ea-37163b5e52c8.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/b922c8b1-9a06-4a9a-a1ea-37163b5e52c8.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "428.4",
        "last_order": "435.3",
        "min_price": "428.0",
        "max_price": "442.0",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 1,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-akroirt.png",
        "is_favorite": false
      },
      {
        "id": 501,
        "base_coin_id": 120,
        "base_coin_name": "Fetch.AI",
        "base_coin_fa_name": "فچ",
        "base_coin_symbol": "FET",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "134510",
        "other_side_each_price": null,
        "quote_coin_volume": "318181024",
        "base_coin_volume": "2365.48",
        "24h_change": "4.993",
        "24h_change_volume": "6397",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "0.75",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/41fd8935-e43d-4aa7-98ec-d6390f3ad887.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/41fd8935-e43d-4aa7-98ec-d6390f3ad887.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "128113",
        "last_order": "134510",
        "min_price": "126053",
        "max_price": "138221",
        "base_coin_decimal": 2,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-fetirt.png",
        "is_favorite": false
      },
      {
        "id": 261,
        "base_coin_id": 523,
        "base_coin_name": "Candy Pocket",
        "base_coin_fa_name": "کندی",
        "base_coin_symbol": "CANDY",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "447.4",
        "other_side_each_price": null,
        "quote_coin_volume": "309801380",
        "base_coin_volume": "692448",
        "24h_change": "-1.993",
        "24h_change_volume": "-9.1",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.0",
        "market_order_base_coin_total_min": "224",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/CANDY.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/CANDY.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "456.5",
        "last_order": "447.4",
        "min_price": "418.7",
        "max_price": "462.7",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 1,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-candyirt.png",
        "is_favorite": false
      },
      {
        "id": 279,
        "base_coin_id": 423,
        "base_coin_name": "Kaspa",
        "base_coin_fa_name": "کاسپا",
        "base_coin_symbol": "KAS",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "6891",
        "other_side_each_price": null,
        "quote_coin_volume": "306228771",
        "base_coin_volume": "44438",
        "24h_change": "4.440",
        "24h_change_volume": "293",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "15",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/Kaspa.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/Kaspa.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "6598",
        "last_order": "6891",
        "min_price": "6555",
        "max_price": "7066",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-kasirt.png",
        "is_favorite": false
      },
      {
        "id": 332,
        "base_coin_id": 490,
        "base_coin_name": "suterusu",
        "base_coin_fa_name": "سوتر",
        "base_coin_symbol": "SUTER",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "25.13",
        "other_side_each_price": null,
        "quote_coin_volume": "281562087",
        "base_coin_volume": "11204221",
        "24h_change": "8.132",
        "24h_change_volume": "1.89",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.00",
        "market_order_base_coin_total_min": "3980",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/SUTER.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/SUTER.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "23.24",
        "last_order": "25.13",
        "min_price": "23.08",
        "max_price": "26.25",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 2,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-suterirt.png",
        "is_favorite": false
      },
      {
        "id": 309,
        "base_coin_id": 513,
        "base_coin_name": "Victoria VR",
        "base_coin_fa_name": "ویکتوریا",
        "base_coin_symbol": "VR",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "1137",
        "other_side_each_price": null,
        "quote_coin_volume": "280353641",
        "base_coin_volume": "246573",
        "24h_change": "1.427",
        "24h_change_volume": "16",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "88",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/VR.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/VR.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "1121",
        "last_order": "1137",
        "min_price": "1121",
        "max_price": "1201",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-vrirt.png",
        "is_favorite": false
      },
      {
        "id": 60,
        "base_coin_id": 64,
        "base_coin_name": "1INCH",
        "base_coin_fa_name": "وان اینچ",
        "base_coin_symbol": "1INCH",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "24044",
        "other_side_each_price": null,
        "quote_coin_volume": "254374243",
        "base_coin_volume": "10579.5",
        "24h_change": "3.335",
        "24h_change_volume": "776",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000",
        "market_order_base_coin_total_min": "4.2",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/bcb2e41a-cd02-4bef-a7a4-95e7f1b05df1.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/bcb2e41a-cd02-4bef-a7a4-95e7f1b05df1.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "23268",
        "last_order": "24044",
        "min_price": "23089",
        "max_price": "24054",
        "base_coin_decimal": 1,
        "quote_coin_decimal": 0,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-1inchirt.png",
        "is_favorite": false
      },
      {
        "id": 246,
        "base_coin_id": 69,
        "base_coin_name": "Terra Classic",
        "base_coin_fa_name": "لونا کلاسیک",
        "base_coin_symbol": "LUNC",
        "quote_coin_id": 524,
        "quote_coin_symbol": "IRT",
        "quote_coin_name": "Toman",
        "quote_coin_fa_name": "تومان",
        "each_price": "6.644",
        "other_side_each_price": null,
        "quote_coin_volume": "252488593",
        "base_coin_volume": "38002497",
        "24h_change": "3.328",
        "24h_change_volume": "0.214",
        "total_min": "100000.00000000",
        "market_order_quote_coin_total_min": "100000.000",
        "market_order_base_coin_total_min": "15052",
        "web_icon": "https://storage.bit24.exchange/exchange/icons/b49342ab-188f-4a0f-ace0-6bacfc0c94a1.png",
        "app_icon": "https://storage.bit24.exchange/exchange/icons/b49342ab-188f-4a0f-ace0-6bacfc0c94a1.png",
        "quote_web_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "quote_app_icon": "https://storage.bit24.exchange/exchange/icons/IRT.png",
        "is_active": 1,
        "first_order": "6.430",
        "last_order": "6.644",
        "min_price": "6.421",
        "max_price": "6.765",
        "base_coin_decimal": 0,
        "quote_coin_decimal": 3,
        "daily_chart_icon": "http://price-storage.bit24.cash/price-pro/daily-kucoin-luncirt.png",
        "is_favorite": false
      }
    ]
  }
}
```


## Get Order Book

Get Order Book

??? code-ref "Reference"

    - Sync Code Reference: [Client.get_order_book](../reference/clients#src.bit24.clients.Client.get_order_book)
    - Async Code Reference: [AsyncClient.get_order_book](../reference/clients#src.bit24.clients.AsyncClient.get_order_book)
    - API Documentation Reference: [Get Order Book](https://docs.bit24.cash/#a283f9354b)

=== "Sync"

    ```python title="get_order_book.py" linenums="1"
    from bit24 import Client

    client = Client("<API_KEY>", "<API_SECRET>")


    def main():
        data = client.get_order_book(
            "USDT", "IRT"
        )
        print(data)


    if __name__ == "__main__":
        main()
    ```

=== "Async"

    ```python title="get_order_book_async.py" linenums="1"
    import asyncio
    from bit24 import AsyncClient

    client = AsyncClient("<API_KEY>", "<API_SECRET>")


    async def main():
        data = await client.get_order_book(
            "USDT", "IRT"
        )
        print(data)


    if __name__ == "__main__":
        asyncio.run(main())
    ```

```json title="output" linenums="1"
{
  "success": true,
  "status_code": 200,
  "error": null,
  "data": {
    "message": "",
    "USDTIRT": {
      "id": 7,
      "market_symbol": "USDTIRT",
      "buy_orders": [
        {
          "market_id": 7,
          "each_price": "61189.0000000000000000",
          "available_amount": "2522.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61183.0000000000000000",
          "available_amount": "1081.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "61161.0000000000000000",
          "available_amount": "999.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61152.0000000000000000",
          "available_amount": "1852.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "61143.0000000000000000",
          "available_amount": "1304.300000000000"
        },
        {
          "market_id": 7,
          "each_price": "61129.0000000000000000",
          "available_amount": "835.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "61119.0000000000000000",
          "available_amount": "1399.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "61105.0000000000000000",
          "available_amount": "2528.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61097.0000000000000000",
          "available_amount": "1920.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "61088.0000000000000000",
          "available_amount": "680.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "61073.0000000000000000",
          "available_amount": "1837.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "61057.0000000000000000",
          "available_amount": "1543.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61049.0000000000000000",
          "available_amount": "396.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "61044.0000000000000000",
          "available_amount": "1053.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "61026.0000000000000000",
          "available_amount": "1367.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "61017.0000000000000000",
          "available_amount": "1642.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "61010.0000000000000000",
          "available_amount": "1287.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "60993.0000000000000000",
          "available_amount": "690.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "60981.0000000000000000",
          "available_amount": "2513.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "60978.0000000000000000",
          "available_amount": "337.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "60966.0000000000000000",
          "available_amount": "2012.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "60953.0000000000000000",
          "available_amount": "1087.600000000000"
        },
        {
          "market_id": 7,
          "each_price": "60935.0000000000000000",
          "available_amount": "96.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "60929.0000000000000000",
          "available_amount": "1591.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "60913.0000000000000000",
          "available_amount": "2758.100000000000"
        },
        {
          "market_id": 7,
          "each_price": "60903.0000000000000000",
          "available_amount": "413.600000000000"
        },
        {
          "market_id": 7,
          "each_price": "57130.0000000000000000",
          "available_amount": "48.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "53107.0000000000000000",
          "available_amount": "70.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "50589.0000000000000000",
          "available_amount": "28.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "49387.0000000000000000",
          "available_amount": "42.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "44877.0000000000000000",
          "available_amount": "44.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "44638.0000000000000000",
          "available_amount": "17.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "41605.0000000000000000",
          "available_amount": "2.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "38988.0000000000000000",
          "available_amount": "97.100000000000"
        },
        {
          "market_id": 7,
          "each_price": "37540.0000000000000000",
          "available_amount": "108.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "35417.0000000000000000",
          "available_amount": "96.100000000000"
        },
        {
          "market_id": 7,
          "each_price": "33277.0000000000000000",
          "available_amount": "105.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "32406.0000000000000000",
          "available_amount": "143.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "30500.0000000000000000",
          "available_amount": "161.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "28632.0000000000000000",
          "available_amount": "84.100000000000"
        }
      ],
      "sell_orders": [
        {
          "market_id": 7,
          "each_price": "61413.0000000000000000",
          "available_amount": "968.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "61423.0000000000000000",
          "available_amount": "370.100000000000"
        },
        {
          "market_id": 7,
          "each_price": "61428.0000000000000000",
          "available_amount": "2193.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61444.0000000000000000",
          "available_amount": "210.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61454.0000000000000000",
          "available_amount": "1941.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "61459.0000000000000000",
          "available_amount": "1349.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "61471.0000000000000000",
          "available_amount": "664.600000000000"
        },
        {
          "market_id": 7,
          "each_price": "61478.0000000000000000",
          "available_amount": "1561.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "61482.0000000000000000",
          "available_amount": "1925.300000000000"
        },
        {
          "market_id": 7,
          "each_price": "61493.0000000000000000",
          "available_amount": "1235.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "61507.0000000000000000",
          "available_amount": "811.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "61510.0000000000000000",
          "available_amount": "1179.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "61521.0000000000000000",
          "available_amount": "2273.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "61530.0000000000000000",
          "available_amount": "212.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "61539.0000000000000000",
          "available_amount": "1582.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61552.0000000000000000",
          "available_amount": "1004.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61559.0000000000000000",
          "available_amount": "608.200000000000"
        },
        {
          "market_id": 7,
          "each_price": "61563.0000000000000000",
          "available_amount": "1290.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "61573.0000000000000000",
          "available_amount": "239.100000000000"
        },
        {
          "market_id": 7,
          "each_price": "61587.0000000000000000",
          "available_amount": "2101.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "61597.0000000000000000",
          "available_amount": "2364.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "61601.0000000000000000",
          "available_amount": "70.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "61611.0000000000000000",
          "available_amount": "112.600000000000"
        },
        {
          "market_id": 7,
          "each_price": "61624.0000000000000000",
          "available_amount": "1606.100000000000"
        },
        {
          "market_id": 7,
          "each_price": "61630.0000000000000000",
          "available_amount": "1070.400000000000"
        },
        {
          "market_id": 7,
          "each_price": "61643.0000000000000000",
          "available_amount": "1356.700000000000"
        },
        {
          "market_id": 7,
          "each_price": "66825.0000000000000000",
          "available_amount": "69.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "70680.0000000000000000",
          "available_amount": "43.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "71477.0000000000000000",
          "available_amount": "29.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "76903.0000000000000000",
          "available_amount": "15.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "82117.0000000000000000",
          "available_amount": "33.300000000000"
        },
        {
          "market_id": 7,
          "each_price": "86728.0000000000000000",
          "available_amount": "27.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "89994.0000000000000000",
          "available_amount": "52.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "94469.0000000000000000",
          "available_amount": "44.600000000000"
        },
        {
          "market_id": 7,
          "each_price": "98720.0000000000000000",
          "available_amount": "30.300000000000"
        },
        {
          "market_id": 7,
          "each_price": "104265.0000000000000000",
          "available_amount": "41.800000000000"
        },
        {
          "market_id": 7,
          "each_price": "109439.0000000000000000",
          "available_amount": "33.000000000000"
        },
        {
          "market_id": 7,
          "each_price": "111344.0000000000000000",
          "available_amount": "31.500000000000"
        },
        {
          "market_id": 7,
          "each_price": "117072.0000000000000000",
          "available_amount": "26.900000000000"
        },
        {
          "market_id": 7,
          "each_price": "124419.0000000000000000",
          "available_amount": "28.700000000000"
        }
      ]
    }
  }
}
```