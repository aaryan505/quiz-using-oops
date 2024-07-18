# quiz-using-oops
this Python project implements a simple quiz application. The application uses three main modules: Question, question_data, and QuizBrain. It creates a list of question objects from provided question data, initializes a quiz with these questions, and then runs the quiz, prompting the user to answer each question until there are no more left


# Quiz Application

This is a simple quiz application built in Python. The application uses object-oriented programming principles to create and manage quiz questions and to handle the quiz logic.

## Table of Contents

- [Description](#description)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

## Description

The Quiz Application allows users to test their knowledge through a series of questions. It leverages three main modules: `Question`, `question_data`, and `QuizBrain`. The application creates a list of question objects from provided question data, initializes a quiz with these questions, and runs the quiz by prompting the user to answer each question until there are no more questions left. Finally, it displays the user's score.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/quiz-application.git
   ```

2. Navigate to the project directory:

   ```bash
   cd quiz-application
   ```

3. (Optional) Create and activate a virtual environment:

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

4. Install any dependencies (if applicable).

## Usage

1. Ensure you have the necessary files: `question_model.py`, `data.py`, and `quiz_brain.py`.

2. Run the main script:

   ```bash
   python main.py
   ```

3. Follow the on-screen prompts to answer each quiz question.

4. After completing the quiz, your final score will be displayed.

## Project Structure

- `question_model.py`: Defines the `Question` class.
- `data.py`: Contains the `question_data`, a list of question dictionaries.
- `quiz_brain.py`: Contains the `QuizBrain` class for quiz logic.
- `main.py`: The main script that initializes and runs the quiz.

### main.py

```python
from question_model import Question
from data import question_data
from quiz_brain import QuizBrain

question_bank = []
for question in question_data:
    question_text = question["text"]
    question_answer = question["answer"]
    new_question = Question(question_text, question_answer)
    question_bank.append(new_question)

quiz = QuizBrain(question_bank)
while quiz.still_has_questions():
    quiz.next_question()

print("You've completed the quiz")
print(f"Your final score was: {quiz.score}/{quiz.question_number}")
```

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. For major changes, please open an issue first to discuss what you would like to change.
