# Software 2 - Class Exercise 8

# Goals
- Add Validation
- Add Generics

# Instructions
## Validation
1. Change Option 1 in `Program` to take JSON as input instead of taking each property as input.  The easiest way would be to take the input from the user as input and deserialize it.
1. Once you finish that, test it.  Here's some JSON you can use:
	```
	{ "Price": 58.89, "Name": "Special dog leash", "Quantity": 23, "Description": "Magical leash that will help your dog not pull hard when going on walks", "Material": "Classified", "LengthInches": 12 }
	```
1. Add the nuget package `FluentValidation`.
1. Follow [this tutorial](https://docs.fluentvalidation.net/en/latest/start.html) to add a validator for `DogLeash`.  Add a folder in the solution for validators.
1. The rules that we want for our class will be the following.
   - Name is required
   - Price is a positive number
   - Quantity is a positive number
   - _If_ description has a value, the minimum number of characters allow is 10.
1. Use the validator in the add method in `ProductLogic`.  Throw a `ValidationException` if the DogLeash isn't valid.
1. Use the following JSON to test. The application should crash.
	```
	{ "Price": 58.89, "Name": "Special dog leash", "Quantity": -10, "Description": "Magical leash that will help your dog not pull hard when going on walks", "Material": "Classified", "LengthInches": 12 }
	```

## Generics
1. Update the method in `ProductLogic` that gets a dog leash by name to now be a generic method that will get any product.
1. Here is the method header to get you started: `public T GetProductByName<T>(string name) where T : Product`. Here are a couple operators that will come in handy:
   - `typeof`
   - `as`
1. Don't forget to test!

Only look at the solution when you get stuck.  We encourage you to talk through this exercise with your classmates!
