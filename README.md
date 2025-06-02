# Currency-Converter
# Fixed exchange rates (example)
exchange_rates = {
    'USD': 1.0,
    'EUR': 0.85,
    'INR': 83.2,
    'JPY': 156.3,
}

def convert_currency(amount, from_currency, to_currency):
    if from_currency not in exchange_rates or to_currency not in exchange_rates:
        return "Invalid currency"
    usd_amount = amount / exchange_rates[from_currency]
    return usd_amount * exchange_rates[to_currency]

print("Currency Converter")
print("Supported currencies: USD, EUR, INR, JPY")

while True:
    try:
        from_curr = input("From currency: ").upper()
        to_curr = input("To currency: ").upper()
        amount = float(input("Amount: "))

        result = convert_currency(amount, from_curr, to_curr)
        print(f"{amount} {from_curr} = {result:.2f} {to_curr}")
    except ValueError:
        print("Invalid amount entered.")
    
    cont = input("Do you want to convert again? (yes/no): ").lower()
    if cont != 'yes':
        break
