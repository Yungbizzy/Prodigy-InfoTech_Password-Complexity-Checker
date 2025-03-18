# Prodigy-InfoTech_Password-Complexity-Checker
# Password Complexity Checker Report

## 1. Introduction
Password security is a fundamental aspect of cybersecurity, ensuring that unauthorized individuals cannot gain access to sensitive data. Weak passwords remain one of the most common vulnerabilities in cybersecurity incidents. The purpose of this project was to develop a **Password Complexity Checker** to evaluate password strength based on multiple security criteria. By implementing this tool, users can receive real-time feedback on their passwords and take necessary actions to enhance their security.

## 2. Objectives
The objectives of this project were:
- To develop a Python-based **Password Complexity Checker**.
- To assess password strength using predefined security criteria.
- To provide feedback to users on how to improve their passwords.
- To enhance password security awareness.

## 3. Methodology
The project was implemented using **Python 3** on **Kali Linux** following these steps:

### 3.1 Development Environment Setup
- Verified the presence of **Python 3** using the command:
  
  python3 --version
  ```
  **Output:**
  Python 3.13.2
  ```
- Installed **Python 3** (if necessary) using:
  sudo apt update
  sudo apt install python3
### 3.2 Script Development
- Created a Python script using:

  nano password_complexity_checker.py

- Implemented the following script:
  ```python
  import re

  def check_password_strength(password):
      """Check the strength of a given password based on multiple criteria."""
      length_criteria = len(password) >= 8
      upper_case_criteria = bool(re.search(r'[A-Z]', password))
      lower_case_criteria = bool(re.search(r'[a-z]', password))
      digit_criteria = bool(re.search(r'[0-9]', password))
      special_char_criteria = bool(re.search(r'[!@#$%^&*(),.?":{}|<>]', password))

      score = sum([length_criteria, upper_case_criteria, lower_case_criteria, digit_criteria, special_char_criteria])

      if score == 5:
          return "✅ Strong password! Your password meets all security criteria."
      elif score == 4:
          return "👍 Good password! Consider adding more variety for extra security."
      elif score == 3:
          return "⚠️ Fair password. Improve by including: Uppercase letter (A-Z), Digit (0-9), or Special character (!@#$%^&*)."
      else:
          return "❌ Weak password. Please add: Uppercase letter (A-Z), Digit (0-9), Special character (!@#$%^&*())."

  def main():
      """Run the password strength checker."""
      print("🔒 Password Complexity Checker 🔒")
      password = input("Enter your password: ")
      print(check_password_strength(password))

  if __name__ == "__main__":
      main()

![image](https://github.com/user-attachments/assets/200f6e98-1373-4c63-b232-c79801b9aa9e)

### 3.3 Execution and Testing
- The script was executed using:
- 
  python3 password_complexity_checker.py
  ```
- The user was prompted to enter a password for evaluation.
- Passwords were tested with different complexity levels to confirm the tool's effectiveness.
- Output messages were validated against expected password strength categories.

## 4. Results
The **Password Complexity Checker** successfully categorized passwords based on their strength. Example outputs from the actual test:

**Example 1 (Good Password):**
```
Enter your password: exponential12aab
Good password! Consider adding more variety for extra security.
```

**Example 2 (Weak Password):**
```
Enter your password: lifeisgood
Weak password. ❌ Please add: Uppercase letter (A-Z), Digit (0-9), Special character (!@#$%^&*()).
```

**Example 3 (Good Password):**
```
Enter your password: ethicalah35shack@1010
Good password! Consider adding more variety for extra security.
```

**Example 4 (Good Password):**
```
Enter your password: almunovpyb-wagrq-qoncy8
Good password! Consider adding more variety for extra security.
```
The tool provided real-time feedback, helping users improve their password security practices.
![image](https://github.com/user-attachments/assets/5df03bbb-05c8-46a3-b995-df9ee0227fcd)

## 5. Limitations
- The tool does not check for commonly used passwords (e.g., '123456', 'password').
- The tool does not enforce password changes but only provides recommendations.
- It does not provide password generation functionality.

## 6. Recommendations
To improve the **Password Complexity Checker**, the following enhancements are suggested:
1. **Integration of Common Password List:**
   - Implement a database of frequently used weak passwords to prevent their usage.
2. **Enhanced Scoring System:**
   - Instead of a simple score, implement a weighted system that provides a percentage-based strength indicator.
3. **Password Suggestions:**
   - Provide auto-generated strong password recommendations for users who need assistance creating secure passwords.
4. **GUI Implementation:**
   - Develop a user-friendly interface for ease of use, making it accessible to non-technical users.

## 7. Conclusion
The **Password Complexity Checker** is an effective tool for evaluating password strength and raising awareness about cybersecurity best practices. By following the recommendations outlined in this report, the tool can be enhanced to provide even greater security for users. This project highlights the importance of strong passwords in protecting sensitive information and mitigating cybersecurity risks.
