import re

def check_length(password):
    return len(password) >= 8  # Minimum length of 8 characters

def check_special_characters(password):
    return bool(re.search(r'[!@#$%^&*(),.?":{}|<>]', password))

def check_uppercase_letters(password):
    return any(char.isupper() for char in password)

def check_lowercase_letters(password):
    return any(char.islower() for char in password)

def check_numbers(password):
    return any(char.isdigit() for char in password)

def analyze_password(password):
    results = {
        "Length": check_length(password),
        "Special Characters": check_special_characters(password),
        "Uppercase Letters": check_uppercase_letters(password),
        "Lowercase Letters": check_lowercase_letters(password),
        "Numbers": check_numbers(password)
    }
    return results

def main():
    password = input("Enter your password: ")
    analysis_result = analyze_password(password)
    print("\nPassword Analysis:")
    for key, value in analysis_result.items():
        print(f"{key}: {'✓' if value else '✗'}")

if __name__ == "__main__":
    main()

