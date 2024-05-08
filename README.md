# Drona Pay Pvt Lt Assignment
JSONLogic Assignment
**Task A :** If the input string has only 3 charecters, please check if it is a Pallindrome and give output "Pallindrome" or "Not a Pallindrome". If input string has more than 3 charecters then output is "Large". 

The logic to determine if an input string is a palindrome is represented in JSONLogic code. Below is the JSONLogic 
code used:
{
  "if": [
    {"===": [{"reverse": {"var": "input"}}, {"var": "input"}]},
    "Palindrome",
    {
      "if": [
        {"===": [{"strlen": {"var": "input"}}, 3]},
        "Not a Palindrome",
        "Large"
      ]
    }
  ]
}
Comment : Input Data
{
  "input": "radar"
}
Output: Large
**Explanation of this code:**

We first check if the input string is equal to its reverse, indicating a palindrome.
If it is, we output "Palindrome".
If it's not a palindrome, we then check if the length of the input string is exactly 3 characters.
If the length is exactly 3 characters, we output "Not a Palindrome".
If the length is not 3 characters, we output "Large".

** Task B:** Now My Second Question was Based on 2 inputs values (transactionamount, transactioncount), we need you to return score = 0 if (totaltransactionamount < 10K, transactioncount < 5 or if either are NULL), if transactionamount >= 10K & transactioncount >=5 then score = 100. 

The logic to calculate the transaction score based on transaction amount and transaction count is represented in JSONLogic code. Below is the JSONLogic 
code used:
{
  "if": [
    {
      "or": [
        {"<": [{"var": "transactionamount"}, 10000]},
        {"<": [{"var": "transactioncount"}, 5]},
        {"===": [{"var": "transactionamount"}, null]},
        {"===": [{"var": "transactioncount"}, null]}
      ]
    },
    0,
    {
      "if": [
        {
          "and": [
            {">=": [{"var": "transactionamount"}, 10000]},
            {">=": [{"var": "transactioncount"}, 5]}
          ]
        },
        100,
        null
      ]
    }
  ]
}


Input Data: 
To use the transaction score calculator, provide input data in the form of a JSON object with two properties: "transactionamount" and "transactioncount". 
{
  "transactionamount": 12000,
  "transactioncount": 6
}

Output: 100
This indicates that the transaction score is 100, as both conditions specified in the logic are met.


