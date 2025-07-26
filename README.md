# Quiz_Game_file_handling-Python
A simple interactive Quiz Game built in Python using file handling techniques. Developed in Google Colab, this CLI game reads questions from a text file and keeps score for the user. Includes restart functionality and clean scoring system.

# 🧠 Quiz Game using Python (File Handling)

This is a simple command-line **Quiz Game** built using Python and developed in **Google Colab**.  
It uses **file handling** to read questions from a `.txt` file and interacts with the user for answers.

---

## 🎮 Features

- 10 Multiple-Choice Questions
- Reads questions from `quiz.txt` file
- Validates user input
- Tracks and displays score
- Allows quiz restart option
- Clean console-based UI

---

## 🚀 How to Run (Google Colab)

1. Open Google Colab: [https://colab.research.google.com](https://colab.research.google.com)

2. Create a new Notebook

3. In the **first cell**, write:
   ```python
   %%writefile quiz.txt
   1. What is the Highest Waterfall in the world?,A. Angel Waterfall,B. Tarabu Falls,C. Jog Falls,D. Niagra Falls,A
   2. Who is known as the father of the nation?,A. Rabindranath Tagore,B. APJ Abdul Kalam,C. Mahatma Gandhi,D. Jawaharlal Nehru,C
   3. Who Wrote "Indian Constitution"?,A. Lal Bahadur Sastry,B. DR.B.R.Ambedkar,C. Sarvepalli RadhaKrishna,D. Bankim chandra Chattarge,B
   4. What is the capital of india?,A. Delhi,B. Kolkata,C. Mumbai,D. Chennai,A
   5. Who is the Prime Minister of India?,A. Manmohan Singh,B. Narendra Modi,C. Rahul Gandhi,D. Draupadi Murumur,B
   6. What is the Highest peak in the world?,A. Kilimanjaroo,B. MT Fiji,C. Mount Everest,D. MT Sinai,C
   7. Who is the inventor of Bulb?,A. Thomas Alva Edison,B. GrahamBell,C. Einsten,D. Darwin,A
   8. Where did Jesus born?,A. Nazareth,B. Jerusalem,C. Getsamane,D. Bethlehem,D
   9. Which year India got independence?,A. 1966,B. 1947,C. 1973,D. 1950,B 
   10. In which country the statue of liberty located?,A. India,B. China,C. USA,D. Japan,C

4. Game Logic

def startquiz(filename):
    try:
        print("------------------------------------------------------")
        print("               Let's Start The Quiz                   ")
        print("------------------------------------------------------")
        while True:
            score = 0
            with open(filename, 'r') as file:
                l = file.readlines()
                total = len(l)

                for i in l:
                    question, a, b, c, d, ans = i.strip().split(',')
                    print("\n" + question)
                    print("\n" + a + "\n" + b + "\n" + c + "\n" + d + "\n")
                    userinput = input("Choose the Correct Option--> A,B,C,D:  ")
                    if userinput.lower() == ans.lower():
                        print("\n✅ Correct Answer!")
                        score += 1
                    else:
                        print(f"\n❌ Wrong Answer! The Correct Answer is: {ans}")

                print("---------------------------------------------------------")
                print("                  !Final ScoreCard!                      ")
                print("---------------------------------------------------------")
                print(f" The Final Score is {score} out of {total}")
                print("=========================================================")
                print("                 !Thanks For Playing!                    ")
                print("=========================================================\n")

            inp = input('🔁 Do You Want to Restart? (Y/N): ')
            if inp.lower() == 'n':
                break

    except FileNotFoundError:
        print("⚠️ File Not Found! Please check if quiz.txt exists.")

startquiz("quiz.txt")


💡 Future Improvements (Suggestions):
- Randomize questions
  Use import random and random.shuffle() to show questions in different order each time.
- Store high scores
  Save the user's name and high score in a new file like highscores.txt.
- Add difficulty levels
  Separate quiz.txt into levels like easy.txt, medium.txt, hard.txt.
- Use JSON instead of CSV-like format
  Make the file more structured and flexible using JSON.
- GUI version using Tkinter or PyQt
  Convert the game to a graphical interface for Windows/Linux apps.
- Online deployment using Streamlit
  Make it web-based and deploy on platforms like Streamlit Cloud or Replit.

🧠 Who is this for?
- Python beginners
- File handling practice
- Students preparing for projects
- Anyone who wants to build a quiz app fast

