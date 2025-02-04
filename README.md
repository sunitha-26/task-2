import random

# Define a set of quiz questions and answers
questions = [
    {"question": "What is the capital of France?", "options": ["A) Berlin", "B) Madrid", "C) Paris", "D) Rome"], "answer": "C"},
    {"question": "Which planet is known as the Red Planet?", "options": ["A) Earth", "B) Mars", "C) Jupiter", "D) Venus"], "answer": "B"},
    {"question": "What is the largest ocean on Earth?", "options": ["A) Atlantic", "B) Indian", "C) Arctic", "D) Pacific"], "answer": "D"},
    {"question": "How many continents are there?", "options": ["A) 5", "B) 6", "C) 7", "D) 8"], "answer": "C"},
    {"question": "Who wrote 'Hamlet'?", "options": ["A) Charles Dickens", "B) William Shakespeare", "C) Mark Twain", "D) Jane Austen"], "answer": "B"}
]

def run_quiz():
    score = 0
    num_questions = len(questions)
    random.shuffle(questions)  # Shuffle questions for randomness
    
    print("Welcome to the Quiz! Answer the following questions:")
    
    for i, q in enumerate(questions, start=1):
        print(f"\nQuestion {i}: {q['question']}")
        for option in q['options']:
            print(option)
        
        user_answer = input("Your answer (A/B/C/D): ").strip().upper()
        
        if user_answer == q['answer']:
            print("Correct!")
            score += 1
        else:
            print(f"Wrong! The correct answer was {q['answer']}.")
    
    print(f"\nQuiz Over! Your final score: {score}/{num_questions}")
    if score == num_questions:
        print("Excellent! You got all answers right!")
    elif score >= num_questions / 2:
        print("Good job! Keep practicing.")
    else:
        print("Better luck next time. Keep learning!")

if __name__ == "__main__":
    run_quiz()
