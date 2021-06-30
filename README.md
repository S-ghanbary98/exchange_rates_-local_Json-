# Exchange Rates Package

### Exchange rate Class

- Exchange class allows object to be created with an initial currency value.
- `rates` function searches json file `exchange_rates.json` looking for currency in object.
- If found then it displays the currency, if not then an error message is displayed.

```python
import json

class Exchange:
    def __init__(self, currency):                   
        self.rates(currency)

    def rates(self, currency):
        file = open("exchange_rates.json")              # Allows file to be read
        currencies = json.loads(file.read())            # allows us to navigate through json file
        
        # Locating currency and rate 
        if currency in currencies['rates'].keys():
            print("{} exchange rate is {}".format(currency.upper(),currencies['rates'][currency.upper()]))
        
        else:
            print("Currency info for {} is not available".format(currency))

        #Prints all rates
    def all_rates(self):
        file = open("exchange_rates.json")
        currencies = json.loads(file.read())

        for key in currencies['rates'].keys():
            print("{} exchange rate is {}".format(key,currencies['rates'][key]))

```

##### Running File

```python
from app.exchange_rate_paser import Exchange

rate1 = Exchange("GBP")
rate2 = Exchange("AUD")

rate1.all_rate
```