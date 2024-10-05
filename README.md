<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# The Syllogism and the truth tables

Final project for the Building AI course


## Summary 2. Context = First teaching of the logic of the Syllogism to children
3. Data and AI techniques = a) Data Used: Major and Minor Premises: These are sentences entered by the user that represent logical statements.
Truth Values: The user enters the truth values ​​(true or false) for the major and minor premises.
b) Choice of Logical Connective: The program chooses the type of logical connective to apply between the premises.


Describe briefly in 2-3 sentences what your project is about. About 250 characters is a nice length!
2. Context = First teaching of the logic of the Syllogism to children
3. Data and AI techniques = a) Data Used: Major and Minor Premises: These are sentences entered by the user that represent logical statements.
Truth Values: The user enters the truth values ​​(true or false) for the major and minor premises.
b) Choice of Logical Connective: The program chooses the type of logical connective to apply between the premises.


## Background

Which problems does your idea solve? How common or frequent is this problem? What is your personal motivation? Why is this topic important or interesting?

C) AI techniques used:
1. Natural Language Processing (NLP):
Subject and Predicate Extraction: The program extracts the subject from the minor premise and the predicate from the major premise using simple string manipulation techniques.
Conclusion Formulation: Combines the subject of the minor premise with the predicate of the major premise to formulate a conclusion.
2. Boolean Logic:
3. Evaluation of Logical Connectives: Uses logical operators to calculate the result of the logical operations chosen by the user (e.g., AND, OR, XOR, implication, logical equivalence, negation).
Human-Computer Interaction:
User Input: The program requires input from the user for the premises, truth values ​​and choices of the logical connective.
Result Output: Prints the result of the logical operation and the truth values ​​of the conclusions.


## How is it used?

Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?
4. How it is used=by high school students
5. Challenges=to practically learn how the Syllogism works and the function of the Truth Tables
6. Thanks=Microsoft “Copilot” for helping in developing the code

Images will make your README look nice!
Once you upload an image to your repository, you can link link to it like this (replace the URL with file path, if you've uploaded an image to Github.)
![Cat](https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg)

If you need to resize images, you have to use an HTML tag, like this:
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg" width="300">


# 2-THE-SILLOGISM-AND-THE-TRUTH-TABLES
1. My idea in brief = “The Syllogism and truth tables”
2. Context = First teaching of the logic of the Syllogism to children
3. Data and AI techniques = a) Data Used: Major and Minor Premises: These are sentences entered by the user that represent logical statements.
Truth Values: The user enters the truth values ​​(true or false) for the major and minor premises.
b) Choice of Logical Connective: The program chooses the type of logical connective to apply between the premises.
C) AI techniques used:
1. Natural Language Processing (NLP):
Subject and Predicate Extraction: The program extracts the subject from the minor premise and the predicate from the major premise using simple string manipulation techniques.
Conclusion Formulation: Combines the subject of the minor premise with the predicate of the major premise to formulate a conclusion.
2. Boolean Logic:
3. Evaluation of Logical Connectives: Uses logical operators to calculate the result of the logical operations chosen by the user (e.g., AND, OR, XOR, implication, logical equivalence, negation).
Human-Computer Interaction:
User Input: The program requires input from the user for the premises, truth values ​​and choices of the logical connective.
Result Output: Prints the result of the logical operation and the truth values ​​of the conclusions.
4. How it is used=by high school students
5. Challenges=to practically learn how the Syllogism works and the function of the Truth Tables
6. Thanks=Microsoft “Copilot” for helping in developing the code
def main():
    # Request the major premise
    major_premise = input("Enter the major premise (e.g., 'The sky is blue'): ")

    # Request the minor premise
    minor_premise = input("Enter the minor premise (e.g., 'The grass is green'): ")

    # Extract the subject of the minor premise
    minor_subject = minor_premise.split()[0]

    # Extract the predicate of the major premise
    major_predicate = ' '.join(major_premise.split()[2:])
    
    # Print the subject of the minor premise followed by the predicate of the major premise
    conclusion = f"{minor_subject} {major_predicate}"
    print("\nConclusion: ", conclusion)

    # Request the truth values of the premises
    major_truth = input("The truth value of the major premise (T/F): ").strip().upper()
    minor_truth = input("The truth value of the minor premise (T/F): ").strip().upper()

    # Convert the truth values to booleans
    A = major_truth == 'T'
    B = minor_truth == 'T'

    # Identify the type of logical connective
    major_connective = identify_logical_connective(major_premise)
    minor_connective = identify_logical_connective(minor_premise)
    # Calculate the truth value of the conclusion based on the identified logical connective
    if major_connective == 'AND' and minor_connective == 'AND':
        result = A and B
    elif major_connective == 'OR' and minor_connective == 'OR':
        result = A or B
    elif major_connective == 'XOR' and minor_connective == 'XOR':
        result = A != B  # XOR
    elif major_connective == 'IMPLIES' and minor_connective == 'IMPLIES':
        result = not A or B  # Logical implication
    elif major_connective == 'NOT_OR' and minor_connective == 'NOT_OR':
        result = not A or B  # Logical implication
    elif major_connective == 'NOT' and minor_connective == 'NOT':
        result = not A
    else:
        result = "Logical connective not recognized or not supported"

    print(f"\nThe result of the operation is: {result}")

    # Print the truth values of the conclusions
    print("\nTruth values of the conclusions:")
    print(f"A and B: {A and B}")
    print(f"A or B: {A or B}")
    print(f"A XOR B: {A != B}")
    print(f"A => B: {not A or B}")
    print(f"not A: {not A}")
    print(f"not B: {not B}")

if __name__ == "__main__":
    main()
