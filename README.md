# **SimpleSwap.io API Python Package**

## How to install?

```shell
pip install simpleswap
```

---

## Usage:

```python
from simpleswap import SimpleSwap

simpleswap = SimpleSwap("YOUR-API-KEY")

#...
```

- Get Your API Key from [partners.simpleswap.io](https://partners.simpleswap.io/)

### Currency API:

##### Get Currency Info:

```python
currency = simpleswap.currency.get_currency("btc")

print(currency.name) # Bitcoin

```

##### Get All Currencies Available:

```python
currencies = simpleswap.currency.get_all_currencies()

for currency in currencies:
    print(currency.name) # Bitcoin, Ethereum, etc

```

---

### Exchange API:

##### Create Exchange:

```python
exchange = simpleswap.exchange.create_exchange(
    "btc",
    "eth",
    0.1,
    "0xBF651C3EC24c099C182410a0F9BF13ac9facFF92")

print(exchange.id) # abdef1234

```

##### Get Exchange by ID:

```python

exchange = simpleswap.exchange.get_exchange("abdef1234")

print(exchange.id) # abdef1234

```

##### Get Exchanges:

```python
after_date = datetime(2024, 9, 18, 0, 0, 0)
# or
before_date = datetime(2024, 9, 19, 0, 0, 0)

exchanges = simpleswap.exchange.get_exchanges(
    limit=50,
    offset=3,
    after_date=after_date,
    before_date=before_date)

for exchange in exchanges:
    print(exchange.id) # abdef1234

```

##### Check Exchange:

```python

is_valid = simpleswap.exchange.check_exchange(
    "btc",
    "eth",
    0.1)

print(is_valid) # True

```

##### Get Estimated Exchanged Value:

```python

value = simpleswap.exchange.get_estimated(
    "btc",
    "eth",
    0.1)

print(value) # 2.52735024

```

##### Get Exchange Ranges for Currency:

```python

ranges = simpleswap.exchange.get_ranges(
    "btc",
    "eth")

print(ranges.min) # 0.001

```

---

### Market API:

##### Get Market Info:

```python

market_rates = simpleswap.market.get_market_info()

for market_rate in market_rates:
    print(market_rate.min) # 0.001
    print(market_rate.max) # 100
    print(market_rate.rate) # 100000.5

```

---

### Pairs API:

##### Get Currency Pairs:

```python

pairs = simpleswap.pairs.get_pairs("btc")

for pair in pairs:
    print(pair) # eth

```

##### Get All Currencies Pairs:

```python

pairs = simpleswap.pairs.get_all_pairs()

for item in pairs.btc:
    print(item) # eth, etc

```

---

Don't forget to view API docs on [simpleswap.io](https://api.simpleswap.io/#/)

Keep in touch with me [@codingtelegrambots](https://t.me/codingtelegrambots)

Be first to join my channel for incomming updates [@drkhedr_projects](https://t.me/drkhedr_projects)

Visit my websites:

- [drkhedr.com](https://drkhedr.com)
- [codingtelegrambots.com](https://codingtelegrambots.com)
