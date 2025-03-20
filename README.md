# PhoneNumbers Information Extractor

This project utilizes the Python predefined library `phonenumbers` to extract information about phone numbers. The library helps us to obtain details such as the carrier (service provider name) and the region to which the phone number belongs.

## Features

- Extract carrier information of a phone number.
- Determine the region associated with a phone number.
- Validate phone numbers.
- Retrieve the timezone of a phone number.

## Getting Started

### Prerequisites

- Python 3.x
- `phonenumbers` library

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/RuchikaTalele12/Get-Info-of-Phone-Number.git
   cd Get-Info-of-Phone-Number
   ```

2. **Install the `phonenumbers` library**:
   ```bash
   pip install phonenumbers
   ```

### Usage

1. **Run the script**:
   ```bash
   python phone_number_info.py
   ```

2. **Input the phone number** with the country code when prompted (e.g., `+1 4155552671`).

3. **Example script**:
   ```python
   import phonenumbers
   from phonenumbers import carrier, geocoder, timezone

   mobileNo = input("Enter Phone number with country code (+xx xxxxxxxxx): ")
   mobileNo = phonenumbers.parse(mobileNo)
   
   if phonenumbers.is_valid_number(mobileNo):
       print('Phone Number belongs to region:', timezone.time_zones_for_number(mobileNo))
       print('Service Provider:', carrier.name_for_number(mobileNo, "en"))
       print('Phone number belongs to country:', geocoder.description_for_number(mobileNo, "en"))
   else:
       print("Please enter a valid mobile number")
   ```

### Example Output

```
Enter Phone number with country code (+xx xxxxxxxxx): +1 4155552671
Phone Number belongs to region: ('America/Los_Angeles',)
Service Provider: AT&T Wireless
Phone number belongs to country: United States
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

This project is licensed under the MIT License.
