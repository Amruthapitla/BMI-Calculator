# BMI-Calculator
ef calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    return round(bmi, 2)

def classify_bmi(bmi):
    if bmi < 18.5:
        return "Underweight"
    elif 18.5 <= bmi < 24.9:
        return "Normal weight"
    elif 25 <= bmi < 29.9:
        return "Overweight"
    else:
        return "Obese"

def main():
    print("Welcome to the BMI Calculator!")

    try:
        weight = float(input("Please enter your weight in kilograms: "))
        height = float(input("Please enter your height in meters: "))

        if weight <= 0 or height <= 0:
            print("Weight and height must be positive numbers. Please try again.")
            return

        bmi = calculate_bmi(weight, height)
        category = classify_bmi(bmi)

        print(f"Your BMI is {bmi}. You are classified as {category}.")

    except ValueError:
        print("Invalid input. Please enter numeric values for weight and height.")

if __name__ == "__main__":
    main()
