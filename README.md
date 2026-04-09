S66: MISSION COMMAND (Customizable Exam Engine)
A mobile-responsive, retro-themed web application designed to help students master financial licensing exams through high-stakes repetition. Originally built for the Series 66, this engine can be easily adapted for the SIE, Series 7, or any other multiple-choice exam.

🛠 Features
Mobile First: Optimized for study sessions on the go.

Save State: Progress is saved to local storage so you don't lose your data.

Audio Feedback: Haptic-style sound effects for "Thrust Nominal" (Correct) or "Critical Failure" (Wrong).

Gamified Telemetry: A live global score tracking your path to orbit (passing).

🔧 How to Adapt for SIE, Series 7, or Other Exams
The entire question bank is controlled by a single JavaScript variable called lib. To change the exam content, follow these steps:

1. Locate the Question Bank
Open index.html and scroll down to the <script> tag. Look for:
const lib = [
    [ /* Pillar 1 Questions */ ],
    [ /* Pillar 2 Questions */ ],
    [ /* Pillar 3 Questions */ ],
    [ /* Pillar 4 Questions */ ]
];
2. Swap the Data
Each question is an "object" inside one of the four pillar arrays. To adapt the game, replace the existing content with your new questions following this exact syntax:
{
    q: "Your question text here?", 
    c: ["Correct Answer", "Distractor 1"], 
    a: 0, 
    f: "Logic explanation for the feedback area."
}
Key Definitions:

q: The question string.

c: An array of choices. Note: The engine automatically generates up to 4 choices by pulling distractors from other questions in the same pillar.

a: The index of the correct answer (usually 0 if you list the correct answer first).

f: The "Logic" or "Rationale" shown after an answer is selected.

3. Update the Menu Labels
If you change the exam to the SIE, you should update the button labels in the HTML div id="menu" section to reflect the correct exam sections:

HTML
<button class="p-btn" onclick="start(0)">01. KNOWLEDGE OF CAPITAL MARKETS...</button>
Local Development
Clone this repository.

Open index.html in any web browser.

No server or database required—runs entirely on client-side JS.

🚀 Deployment
This project is pre-configured for GitHub Pages.

Push your changes to the main branch.

Go to Settings > Pages.

Select the main branch as your source.

Why the logic matters
The engine is designed to be "mean" but fair. It randomizes the gate sequence every time you start a pillar, ensuring that you don't just memorize the order of answers, but actually understand the logic behind the regulatory environment.

Instructions for the user:
Click the Add file button in your GitHub repo.

Name it README.md.

Paste the text above and click Commit changes.

How are you planning to distribute the link once you've got it live? Groups on Reddit or Discord might find this really helpful!
