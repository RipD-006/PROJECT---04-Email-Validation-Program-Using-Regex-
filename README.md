# [PROJECT-04] Advanced Email Validation Program:
This Python project provides an advanced email address validation system that combines both regular expression (Regex) and DNS lookup techniques to ensure email addresses are both syntactically and domain-valid. The goal of this project is to ensure that an email adheres to the correct format, domain and syntax rules commonly used for email addresses.
1) REGEX VALIDATION: The first layer of validation checks the email address format based on a widely accepted regular expression pattern. This ensures that the email follows the correct syntax, such as proper characters before and after the "@" symbol, a valid domain name, and an appropriate domain extension (e.g., .com, .org).
2) DNS LOOKUP: Once the format is verified, the second layer performs a DNS query to ensure that the domain of the email address actually exists and has valid mail exchange (MX) records. This step confirms that the email domain is capable of receiving messages, adding an extra layer of confidence in the email's deliverability.

# Features:
1) SYNTAX VALIDATION: The project checks whether the email follows the standard structure, including a local part, an "@" symbol, and a domain part (i.e. username@domain.com). This validates the presence of "@" symbol, valid characters in the local and domain parts, and properdomain name structure (i.e. ".com", ".org", ".edu", ".in")
2) DOMAIN VALIDATION: The system checks whether the domain part of the email corresponds to a real domain. This is done by checking if the domain is valid and reachable domain through DNS lookup. Verification here is done if the domain contains at least one valid MX (Email Exchange) record, which confirms it can recieve emails.
3) REGEX PATTERN MATCHING: Regular Expression (REGEX) Pattern Matching utilizes regular expression to perform a quick and efficient check on the overall structure of the email address. This includes rules such as local part can contain letters, numbers and special characters; domain part must have a vaild structure with at least one "." seperating the domain and the Top-Level-Domain (TLD).
4) EMAIL FORMAT SUGGESTIONS: If the email address is invalid the system can provide suggestions for correcting common mistakes (i.e. Missing "@"; Incorrect Domain; or Invalid Characters.
5) USER-FRIENDLY INTERFACE: A simple and interactive command-line interface (CLI) is available to input Email Addresses, with clear success or error messages indicating the result of the validation check.

# Required Libraries & Dependencies:
[re] : Python’s regular expression module for basic syntax validation.

[dns.resolver] : A DNS resolver library used to check the validity of the domain’s MX records.
email-validator: A third-party package for more comprehensive email validation, including domain checks

# Installation:
The REGEX module is part of the standard library and its syntax is re, meaning it is included with Python by default. Therefore, you do not need to install the re module separately. You can use it directly in your code without any additional installation steps.
  
    import re

To use DNS lookups as part of your project (e.g., checking MX records for email validation), you will need to install the dnspython package, which is not part of the standard library.
To install it, you can run:

    pip install dnspython

# Program Logic Workflow:
The user inputs an email address, e.g., example@domain.com.
The script runs syntax checks using regular expressions to ensure the email is structured correctly.
If the syntax is valid, it performs a DNS lookup to verify if the domain exists and if it can accept emails.
The result is presented to the user:
"Valid email address."
"Invalid email address. Suggestions: Check for typos in the domain part."
Potential Enhancements:

# Simplified Code Version : [Advanced Email Validation Program]

    import re       # Importing the "REGEX" module.
    email_condition = "^[a - z] + [\._] ? [a - z 0 - 9] + [@]\w + [.]\w {2 , 3} $"

    user_email = input("Enter Email ID: ")

    if re.search(email_condition , user_email):
        print("Valid Email.")
    else:
        print("Invalid Email.")

# Future Enhancement Scopes:
Further future enhancements include:
1) Integration with third-party email validation APIs for more advanced checks (e.g., verifying if the email is disposable or if it exists on common spam lists).
2) Adding a GUI for more user interaction, especially for non-programmers.
3) Extend validation to check for disposable or temporary email services
