# 📘 GitHub Sandbox Contribution Instructions

**Project**: [confident\_quizes](https://github.com/adamrossnelson/confident_quizes)  
**Goal**: Contribute a quiz with 8–10 multiple-choice Python questions as a plain text file.

---

## **📌 Before You Start**

✅ Make sure you have:

* A GitHub account (if working in a group only one member / at least one member will need an account).
* For absolute beginners review: [A brief introduction to Git for beginners | GitHub](https://youtu.be/r8jQ9hVA2qs?si=MNsW2k5A0gveRMjG).
* For more advanced students review [Intro, Config, Creating a Repo - Version Control with Git](https://youtu.be/4UhGzmijRtM?si=kekn8PwNfAW-IEEs).
* Git installed on your local machine (or one group member to have git installed) - Above videos will assist with installation.
* A plain text editor (VS Code, Sublime, Jupyter Lab, or similar).

✅ Suggested: Work in teams of 4–5. Assign one computer as the "main workstation" for submitting your team's quiz.

---

## **🧭 Step-by-Step Instructions**

### **🔁 Step 1: Fork the Main Repository**

1. Go to this link:  
    👉 [https://github.com/adamrossnelson/confident\_quizes](https://github.com/adamrossnelson/confident_quizes)  
2. In the top-right corner, click **Fork** to create a copy under your GitHub account.

---

### **💻 Step 2: Clone Your Fork to Your Local Machine**

On your team’s main workstation:

1. Navigate to your fork you’ll be at something like:

   `https://github.com/your-username/confident_quizes`

2. Click the green **Code** button and copy the HTTPS URL.  
   Open your terminal (or Git Bash),
   be sure to navigate to the directory where you want to clone the repository,
   and run:

   `git clone https://github.com/your-username/confident_quizes.git`

3. Move into the cloned directory:

   `cd confident_quizes`

---

### **📝 Step 3: Create Your Quiz File**

Inside the `confident_quizes` folder, create a new folder named `submissions/` if it doesn’t exist:

`mkdir submissions`

Inside `submissions/`, create a new file named like this:

`groupNN_quiz.txt` (e.g., `group03_quiz.txt`)

Open the file in a plain text editor and write 8–10 **multiple choice Python quiz questions** in this format:

`1. What does the 'len()' function do in Python?`  
`   a) Counts the number of characters in a number`  
`   b) Returns the length of an object`  
`   c) Creates a new list`  
`   d) Converts to lowercase`

Save the file.

---

### **➕ Step 4: Stage and Commit Your Changes**

In the terminal:

`git add submissions/groupNN_quiz.txt`

Then:

`git commit -m "Add quiz from Group NN"`

---

### **☁️ Step 5: Push to Your Fork on GitHub**

`git push`

---

### **🔀 Step 6: Submit a Pull Request (PR)**

1. Go to your forked repo on GitHub.

2. You should see a **“Compare & pull request”** button. Click it.

3. Confirm the pull request is going **from your fork's `main` branch** **into**

   `adamrossnelson/confident_quizes:main`.

4. In the PR description, include:

   * Your group number  
   * Group member names (optional)  
   * One thing you learned about Git

5. Click **Create pull request**.
