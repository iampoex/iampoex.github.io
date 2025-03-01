# IAM Policy Explainer

A web tool that helps explain AWS Identity and Access Management (IAM) policies by breaking down their statements, conditions, and operators in a human-readable format.

---

## 📋 **Features**

- Parses and explains valid JSON-format AWS IAM policies.
- Provides details for each statement, including:
  - Effect (Allow/Deny)
  - Principal (who the policy applies to)
  - Action (what operations are permitted or denied)
  - Resource (what AWS resources are targeted)
  - Conditions with logical operators like AND, OR, and NOR.
- Recognizes standard IAM condition operators (e.g., StringEquals, IpAddress, ArnEquals).
- Highlights policy elements in a structured and easy-to-read format.
- Offers inline notes for custom condition keys.
- Responsive design, optimized for both desktop and mobile use.

---

## 🛠️ **How to Use**

1.	Open the tool in a web browser.
2.	Paste your IAM policy (in JSON format) into the provided text area.
3.	Click the “Explain Policy” button to generate an explanation.
4.	View the breakdown of each policy statement.
5.	Optionally, click “Clear” to reset the input and output fields.

---

## 🔍 **Example**

### Input Policy:
```json
{
  "Version": "2012-10-17",
  "Statement": {
    "Effect": "Allow",
    "Action": "s3:PutObject",
    "Resource": "arn:aws:s3:::my-bucket/*",
    "Condition": {
      "StringEquals": {
        "aws:username": "johndoe"
      }
    }
  }
}
```
### Output Explanation:
```
Statement 1:
Effect: Allow
Action(s): s3:PutObject — these specify the AWS service operations being affected.
Resource(s): arn:aws:s3:::my-bucket/* — The targeted AWS resource(s).
Condition(s): StringEquals (Exact matching, case sensitive): aws:username matches (johndoe)
```

---

## 🚧 **Limitations**
•	**No AWS Service Reference:**

This tool does not cross-reference the Actions, Resources, and Condition keys with the AWS Service Authorization Reference (AWS Service Reference Documentation).

•	**Deeply Nested Structures:**

Complex, deeply nested policy elements may not be fully parsed or explained.

•	**Custom Condition Keys:**

The tool may not provide a detailed explanation for custom-defined condition keys outside of AWS’s standard keys.

•	**Valid JSON Only:**

The tool requires a correctly formatted JSON policy to work. Incorrect JSON will result in an error.

---

## ⚙️ **Technical Details**

**HTML/CSS/JavaScript**
- The tool is built using HTML5, CSS3, and vanilla JavaScript.
- It features responsive styling for mobile and desktop screens.
- Core functionality is implemented in the explainPolicy() function.

**Meta Information**
- Author: [Reese Gerjekian](https://github.com/rgerjeki)
- Website: [IAM Policy Explainer](https://iampoex.github.io)
- Description: A web tool to simplify and demystify AWS IAM policies.

---

## 🎨 **Customization**

You can modify or extend the tool to:
- Add more AWS condition operators and explanations.
- Integrate with AWS service references for action and resource validation.
- Enhance UI/UX with additional features such as policy saving and sharing.
