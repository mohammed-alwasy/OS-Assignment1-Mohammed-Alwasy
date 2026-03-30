# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

I learned that multithreading allows a single process to execute multiple tasks concurrently to boost performance. We explored the critical difference between basic concurrency and true parallelism on multicore systems. I found the mapping models between user and kernel threads—specifically the One-to-One, Many-to-One, and Many-to-Many models—very interesting. Seeing these concepts applied practically through the Java Thread Library for thread creation and management really helped solidify my understanding. Finally, learning about Amdahl's Law was a great reminder that performance gains from adding cores are always limited by the program's sequential parts.

---

## Question 2: What was the most challenging part of this assignment?

The most challenging part of this assignment was implementing the waiting time feature. It was difficult to understand when to update the arrival time and how to correctly calculate the total waiting time. This required a clear understanding of how processes move in and out of the ready queue. At first, I made mistakes in tracking the time, which gave incorrect results. This challenge is related to the concept of scheduling in multithreading. I solved it by testing the program step by step and reviewing the logic carefully.


---

## Question 3: How did you overcome the challenges you faced?

I overcame the challenges by first setting up my development environment properly. At the beginning, I faced problems because Java was not installed on my computer, and I had also forgotten to install Git. After installing both tools, I was able to run and test the code. I also sought help from a friend who guided me through using Git and understanding the project structure. Additionally, I debugged the program step by step and carefully reviewed the code to ensure each feature worked correctly. This approach helped me complete the assignment successfully.


---

## Question 4: How can you apply multithreading concepts in real-world applications?

Multithreading is crucial in web browsers, where one thread renders the page while another downloads data simultaneously. In video games, applying the multicore programming concepts we studied allows separate threads to handle physics, audio, and graphics in true parallelism. This prevents the system from lagging and ensures a highly responsive user experience. Similarly, mobile apps rely on multithreading so the main user interface doesn't freeze while waiting for background network requests to finish. By utilizing user and kernel thread mapping models, developers can efficiently distribute these concurrent tasks across modern hardware. Ultimately, applying these concepts transforms sluggish, sequential programs into fast, efficient applications.

---

## Additional Reflections (Optional)

### What would you like to learn more about?

[Any topics related to threading, concurrency, or operating systems that you're curious about?]

---

### How confident do you feel about multithreading concepts now?

[Rate yourself and explain: Beginner / Intermediate / Confident]

[Explain your rating - what do you understand well? What needs more practice?]

---

### Feedback on the assignment

[Any comments about the assignment? Was it helpful? Too easy/hard? Suggestions for improvement?]
