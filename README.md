Task 1
def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

def celsius_to_kelvin(celsius):
    return celsius + 273.15

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

def fahrenheit_to_kelvin(fahrenheit):
    return (fahrenheit - 32) * 5/9 + 273.15

def kelvin_to_celsius(kelvin):
    return kelvin - 273.15

def kelvin_to_fahrenheit(kelvin):
    return (kelvin - 273.15) * 9/5 + 32

def convert_temperature(value, unit):
    if unit.lower() == 'c':
        celsius = float(value)
        fahrenheit = celsius_to_fahrenheit(celsius)
        kelvin = celsius_to_kelvin(celsius)
        return fahrenheit, kelvin
    elif unit.lower() == 'f':
        fahrenheit = float(value)
        celsius = fahrenheit_to_celsius(fahrenheit)
        kelvin = fahrenheit_to_kelvin(fahrenheit)
        return celsius, kelvin
    elif unit.lower() == 'k':
        kelvin = float(value)
        celsius = kelvin_to_celsius(kelvin)
        fahrenheit = kelvin_to_fahrenheit(kelvin)
        return celsius, fahrenheit
    else:
        return "Invalid unit"

def main():
    value = input("Enter the temperature value: ")
    unit = input("Enter the unit of measurement (C, F, or K): ")

    converted_values = convert_temperature(value, unit)

    if isinstance(converted_values, tuple):
        if unit.lower() == 'c':
            print(f"{value} degrees Celsius is equal to {converted_values[0]} degrees Fahrenheit and {converted_values[1]} Kelvin.")
        elif unit.lower() == 'f':
            print(f"{value} degrees Fahrenheit is equal to {converted_values[0]} degrees Celsius and {converted_values[1]} Kelvin.")
        elif unit.lower() == 'k':
            print(f"{value} Kelvin is equal to {converted_values[0]} degrees Celsius and {converted_values[1]} Fahrenheit.")
    else:
        print(converted_values)

if __name__ == "__main__":
    main()
