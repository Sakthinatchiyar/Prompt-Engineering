PROMPT ENGINEERING

1. Introduction
Prompt Engineering is the process of designing and improving instructions given to Artificial Intelligence models to obtain accurate, relevant and consistent responses.
This experiment explores three important prompt engineering techniques:
Zero-shot and Few-shot Prompting
Chain-of-Thought Prompting
Structured Output Prompting
The main objective is to understand how different prompting techniques influence the quality, accuracy and consistency of AI-generated responses.
2. Experiment 1: Zero-shot vs Few-shot Prompting
Objective
To compare the performance of zero-shot and few-shot prompting using a sentiment classification task.
Task
Classify customer reviews into Positive, Negative or Neutral categories.
A. Zero-shot Prompting
Prompt Used:
You are a sentiment analysis assistant.
Classify each customer review into one of these three categories:
Positive
Negative
Neutral
Return only the sentiment category without any explanation.
Review: "The product quality is excellent, and delivery was very fast."
Actual AI Output:
Positive
B. Few-shot Prompting
Prompt Used:
You are a sentiment analysis assistant.
Classify customer reviews into one of these three categories:
Positive
Negative
Neutral
Follow the classification pattern shown in these examples.
Example 1:
Review: "I love this product. It works perfectly."
Sentiment: Positive
Example 2:
Review: "The product stopped working after two days."
Sentiment: Negative
Example 3:
Review: "The package arrived yesterday."
Sentiment: Neutral
Example 4:
Review: "Excellent customer service and fast delivery."
Sentiment: Positive
Now classify this new review.
Review: "The product quality is excellent, and delivery was very fast."
Return only the sentiment category without any explanation.
Actual AI Output:
Positive
Comparison
Criteria
Zero-shot
Few-shot
Examples
0
4
Output
Positive
Positive
Correctness
Correct
Correct

Analysis
Zero-shot prompting correctly classified the review without any examples. Few-shot prompting also produced the correct result after receiving four examples.
Both techniques achieved the same result in this test. Few-shot prompting helped establish a clear classification pattern, but did not improve accuracy for this particular review.
3. Experiment 2: Chain-of-Thought Prompting
Objective
To compare direct prompting with step-by-step prompting using a multi-step mathematical problem.
Problem
A shopkeeper buys 5 notebooks for ₹40 each. He sells each notebook for ₹55. What is his total profit?
A. Direct Prompting
Prompt Used:
Solve the following math problem and provide only the final answer.
A shopkeeper buys 5 notebooks for ₹40 each. He sells each notebook for ₹55. What is his total profit?
Actual AI Output:
₹75
B. Step-by-Step Prompting
Prompt Used:
Solve the following math problem by breaking it into clear steps. Show the calculation for each step and provide the final answer.
A shopkeeper buys 5 notebooks for ₹40 each. He sells each notebook for ₹55. What is his total profit?
Actual AI Output:
Step 1: Calculate the total cost price.
Cost price of 1 notebook = ₹40
Number of notebooks = 5
Total Cost Price = 5 × 40 = ₹200
Step 2: Calculate the total selling price.
Selling price of 1 notebook = ₹55
Total Selling Price = 5 × 55 = ₹275
Step 3: Calculate the total profit.
Profit = Total Selling Price − Total Cost Price
Profit = ₹275 − ₹200 = ₹75
Final Answer: ₹75
Comparison
Criteria
Direct Prompt
Step-by-Step Prompt
Final answer
₹75
₹75
Correctness
Correct
Correct
Calculation
Not shown
Clearly shown
Explanation
No
Yes

Analysis
Both prompting techniques produced the correct answer. However, step-by-step prompting provided a detailed explanation of the calculation process.
It improved the understandability and verifiability of the answer, although it did not improve final-answer accuracy in this example.
4. Experiment 3: Structured Output (JSON)
Objective
To generate valid JSON output by extracting structured information from customer payment messages.
JSON Schema
The required JSON object contains three fields:
name: Customer name (String)
date: Transaction date (YYYY-MM-DD)
amount: Payment amount (Number)
Prompt Used
You are a data extraction assistant.
Extract customer payment information from the following five messages.
Return the result as a valid JSON array containing five objects.
Each object must contain exactly these three fields:
"name": Customer's name as a string.
"date": Transaction date in YYYY-MM-DD format.
"amount": Payment amount as a number without currency symbols.
Rules:
Do not add explanations or comments.
Use double quotes for JSON keys and string values.
Do not include trailing commas.
If any information is missing, use null.
Return valid JSON only.
Test Input 1:
"John Smith paid ₹1500 on 5 November 2026 for his monthly subscription."
Test Input 2:
"On 12 October 2026, Priya Sharma made a payment of ₹2500."
Test Input 3:
"Rahul Kumar transferred ₹800 on 20 September 2026."
Test Input 4:
"Anita paid ₹1200 on 1 November 2026."
Test Input 5:
"Payment of ₹3000 was received from David Wilson on 8 November 2026."
Actual AI Output
The AI returned a JSON array containing five objects with the following extracted information:
[
{
"name": "John Smith",
"date": "2026-11-05",
"amount": 1500
},
{
"name": "Priya Sharma",
"date": "2026-10-12",
"amount": 2500
},
{
"name": "Rahul Kumar",
"date": "2026-09-20",
"amount": 800
},
{
"name": "Anita",
"date": "2026-11-01",
"amount": 1200
},
{
"name": "David Wilson",
"date": "2026-11-08",
"amount": 3000
}
]
Test Results
Test
Name
Date
Amount
Result
1
Correct
Correct
Correct
Pass
2
Correct
Correct
Correct
Pass
3
Correct
Correct
Correct
Pass
4
Correct
Correct
Correct
Pass
5
Correct
Correct
Correct
Pass

Success Rate:
5/5 × 100 = 100%
Analysis
The AI successfully extracted all five customer records with the correct names, dates and payment amounts.
Explicit field definitions, date formatting instructions, JSON formatting rules and multiple test inputs helped improve output consistency.
The experiment demonstrated how structured prompting can convert unorganized text into machine-readable information.
Note: The extracted values passed all five tests. Strict JSON syntax validation should also be performed on the original unescaped response.
5. Overall Comparison
Technique
Task
Result
Zero-shot
Sentiment classification
Correct
Few-shot
Sentiment classification
Correct
Chain-of-Thought
Mathematical reasoning
Correct
Structured Output
JSON data extraction
5/5 correct

6. Key Learnings
Zero-shot prompting is useful for simple tasks that require no examples.
Few-shot prompting helps the AI understand the expected response pattern.
Chain-of-Thought prompting improves the clarity and verifiability of multi-step answers.
Structured output prompting helps generate organized and machine-readable information.
Clear instructions and explicit formatting requirements improve response consistency.
7. Conclusion
This practical experiment helped me understand the importance of Prompt Engineering in improving AI interactions.
I explored zero-shot, few-shot, chain-of-thought and structured output prompting using ChatGPT.
The experiments demonstrated that providing examples, breaking problems into steps and defining output formats can make AI responses more understandable and consistent.
Overall, I learned how to design effective prompts and evaluate AI-generated outputs through practical testing.

