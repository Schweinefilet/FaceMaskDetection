# 1. Face Mask Detection
- Link Colab: https://colab.research.google.com/drive/1RKxLwq8t2bvUmWAP-8xQQutW2W_R6XN6?usp=sharing

# 2. Assistant
## 2.1. Library
- `pyttsx3`: Convert Text to Speech
- `SpeechRecognition`: Convert Speech to Text
- `fuzzywuzzy`: Calculate the similarity of two texts
- `playsound`: Open audio file in application

## 2.2. Processing
### 2.2.1. Preparing questions and answers
- Prepare questions and corresponding answers for each question.
- **Questions** in `Question.txt` and **Answers** in `Answer.txt`
- Each question and each answer is only on one line
### 2.2.2. Startup
- Read all questions and answers from the file `Question.txt` and `Answer.txt`.
- Use `pyttsx3` to greetings.
- Start microphone and filter noise.
### 2.2.3. Communicating with visitors
- Visitor asks and the system will record the sound through the **Microphone**
- Use library `SpeechRecognition` to convert **audio** to **text**
- For each question in the list, the system uses the library `fuzzywuzzy` to calculate the similarity % to the visitor's question.
- Find the question with the highest similarity.
    - If this similarity is less than 70%, the system will conclude that none of the questions in the list match and say "indiscernible."
    - If not, the system will respond with the corresponding answer.
- Ask if the visitor wants to know any other information, if not, the system will play the `goodbye` audio and return to the first step.
