# quiz-code-
using python make quiz-code .
import random

# List of 50 questions
questions = [
    {
        "question": "What is the capital of France?",
        "options": ["Berlin", "Madrid", "Paris", "Rome"],
        "answer": "Paris"
    },
    {
        "question": "Which planet is known as the Red Planet?",
        "options": ["Earth", "Mars", "Jupiter", "Saturn"],
        "answer": "Mars"
    },
    {
        "question": "What is the largest ocean on Earth?",
        "options": ["Atlantic", "Indian", "Southern", "Pacific"],
        "answer": "Pacific"
    },
    {
        "question": "Who wrote 'Romeo and Juliet'?",
        "options": ["William Shakespeare", "Jane Austen", "Mark Twain", "Charles Dickens"],
        "answer": "William Shakespeare"
    },
    {
        "question": "What is the hardest natural substance on Earth?",
        "options": ["Gold", "Diamond", "Iron", "Platinum"],
        "answer": "Diamond"
    },
    {
        "question": "In which year did World War II end?",
        "options": ["1945", "1939", "1918", "1965"],
        "answer": "1945"
    },
    {
        "question": "Which element has the chemical symbol 'O'?",
        "options": ["Oxygen", "Osmium", "Ozone", "Oganesson"],
        "answer": "Oxygen"
    },
    {
        "question": "What is the smallest country in the world?",
        "options": ["Monaco", "Vatican City", "San Marino", "Liechtenstein"],
        "answer": "Vatican City"
    },
    {
        "question": "Which country is home to the kangaroo?",
        "options": ["South Africa", "Australia", "Canada", "India"],
        "answer": "Australia"
    },
    {
        "question": "Who painted the Mona Lisa?",
        "options": ["Vincent van Gogh", "Leonardo da Vinci", "Pablo Picasso", "Claude Monet"],
        "answer": "Leonardo da Vinci"
    },
    {
        "question": "What is the longest river in the world?",
        "options": ["Amazon", "Nile", "Yangtze", "Mississippi"],
        "answer": "Amazon"
    },
    {
        "question": "Which language is the most spoken worldwide?",
        "options": ["English", "Mandarin Chinese", "Spanish", "Hindi"],
        "answer": "Mandarin Chinese"
    },
    # Add more questions here (up to 50)
    {
        "question": "Which gas do plants absorb from the atmosphere during photosynthesis?",
        "options": ["Oxygen", "Carbon Dioxide", "Nitrogen", "Methane"],
        "answer": "Carbon Dioxide"
    },
    {
        "question": "Which animal is known as the 'King of the Jungle'?",
        "options": ["Lion", "Tiger", "Elephant", "Giraffe"],
        "answer": "Lion"
    },
    # Add additional questions as necessary...
]

# Function to ask questions
def ask_question(question, options, correct_answer):
    print(f"\n{question}")
    for i, option in enumerate(options, 1):
        print(f"{i}. {option}")
    
    # Get user input and validate
    while True:
        try:
            answer = int(input("\nYour answer (1-4): "))
            if 1 <= answer <= 4:
                break
            else:
                print("Please enter a number between 1 and 4.")
        except ValueError:
            print("Invalid input. Please enter a number.")
    
    if options[answer - 1] == correct_answer:
        print("Correct!")
        return 1
    else:
        print(f"Wrong! The correct answer is {correct_answer}.")
        return 0

# Main function to run the quiz
def run_quiz():
    random.shuffle(questions)  # Shuffle the questions to randomize the quiz
    score = 0
    total_questions = len(questions)

    print("Welcome to the Python Quiz!")
    print(f"Answer the following {total_questions} questions:")

    for i, q in enumerate(questions, 1):
        print(f"\nQuestion {i}/{total_questions}")
        score += ask_question(q["question"], q["options"], q["answer"])

    print(f"\nYour final score is {score}/{total_questions}")
    print("Thanks for playing!")

# Start the quiz
if __name__ == "__main__":
    run_quiz()
