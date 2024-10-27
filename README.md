# Basic-Quiz-Game-
print( " *Welcome to Quiz Game * ")
quiz = [
    {
        "question": "Who is the prime minister of india?",
        "options": ["A) Narendra Modi", "B) Rahul Gandhi", "C) N. Chandrababu Naidu", "D) Amit Shah"],
        "answer": "A"
    },
    {
        "question": "What is the capital of india?",
        "options": ["A) Mumbai ", "B) Delhi", "C) Hyderabad", "D) Chennai"],
        "answer": "B"
    },
    {
        "question": "What is the largest ocean on Earth?",
        "options": ["A) Atlantic", "B) Indian", "C) Pacific", "D) Arctic"],
        "answer": "C"
    }
]
def ask_question(question_data):
    print("\n" + question_data["question"])
    for option in question_data["options"]:
        print(option)
    
    while True:
        user_answer = input("Your answer (A, B, C, or D): ").upper()
        if user_answer in ['A', 'B', 'C', 'D']:
            return user_answer
        else:
            print("Invalid input, please choose A, B, C, or D.")
def check_answer(user_answer, correct_answer):
    if user_answer == correct_answer:
        print("Correct!")
        return True
    else:
        print(f"Incorrect! The correct answer was {correct_answer}.")
        return False 
def run_quiz():
    score = 0
    total_questions = len(quiz)
    
    for question_data in quiz:
        user_answer = ask_question(question_data)
        if check_answer(user_answer, question_data["answer"]):
            score += 1
    
    print(f"\nQuiz Completed! Your final score is {score}/{total_questions}.")
if __name__ == "__main__":
    run_quiz()
