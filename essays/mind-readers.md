---
layout: essay
type: essay
title: "(Most) People Aren't Mind Readers"
# All dates must be YYYY-MM-DD format!
date: 2026-09-10
published: true
labels:
  - Questions
  - Communication
  - StackOverflow
---

<img width="300px" class="rounded float-start pe-4" src="../img/mind-readers/mind-readers.jpeg">

Unfortunately we live in a world where the at least the vast majority of people aren't mind readers. If most people were, then getting help from people, whether that be at a shop, when you're lost, or in any other situation where you would like instant help without having to explain anything. Because this is not our reality, we must be sure to ask specific questions with enough context, or smart questions, to be able to get the help we need the fastest. This is especially important in the context of software engineering, as every software engineer will get stuck eventually and have to turn to other software engineers or the broader internet community to get help, and smart questions help get answers quickly and effectively. To explain examples of smart questions and not-so-smart questions, I will show you two very different questions both posted on StackOverflow, a place where software engineers go to ask questions and get answers from the community (or where ChatGPT pulls from to give you an answer to your prompt).

## An Example of a Smart Question

The first question I will discuss is one about Java titled "Why is conditional processing of a sorted array faster than of an unsorted array?", which you may be able to clearly tell from the title alone, is about an if statement (a conditional) being run on every element of an array. The user noted that sorting the array made it run about six times faster, even though it theoretically should not matter. The user additionally stated that they ran the same program in a different programming language and still got the same result. Below is the program in C++ (the if statement is after the "// Test" comment):

```c++
// Source - https://stackoverflow.com/q/11227809
// Posted by GManNickG, modified by community. See post 'Timeline' for change history
// Retrieved 2026-09-10, License - CC BY-SA 4.0

#include <algorithm>
#include <ctime>
#include <iostream>

int main()
{
    // Generate data
    const unsigned arraySize = 32768;
    int data[arraySize];

    for (unsigned c = 0; c < arraySize; ++c)
        data[c] = std::rand() % 256;

    // !!! With this, the next loop runs faster.
    std::sort(data, data + arraySize);

    // Test
    clock_t start = clock();
    long long sum = 0;
    for (unsigned i = 0; i < 100000; ++i)
    {
        for (unsigned c = 0; c < arraySize; ++c)
        {   // Primary loop.
            if (data[c] >= 128)
                sum += data[c];
        }
    }

    double elapsedTime = static_cast<double>(clock()-start) / CLOCKS_PER_SEC;

    std::cout << elapsedTime << '\n';
    std::cout << "sum = " << sum << '\n';
}
```

Within three minutes of asking the question, the user got a short but true answer that the issue was that the code was making bad predictions (a.k.a. branching) on the unsorted array and more accurate predictions on the sorted array. The most upvoted (agreed upon) comment only five minutes after asking the question has a much more in depth explanation about branch prediction and even provides work arounds to make the time the program takes between sorted and unsorted arrays essentially the same. 

This question has many hallmarks of a smart question, as the title is very descriptive, the description is detailed and clear, and shows that they tried to think of the reason for this issue as they were able to replicate the issue in another language, proving it was not a language-specific issue. As a result of this smart question, they were able to quickly get many detailed answers explaining why this problem occured. To read the full thread for this question, [click here](https://stackoverflow.com/questions/11227809/why-is-conditional-processing-of-a-sorted-array-faster-than-of-an-unsorted-array).

## Example of a Not-So-Smart Question

The second question I will discuss is one titled "Android Jules Pattern Build". Although not very obvious from the title, this question is about adding support for Google Jules, an AI agent, in their Android app. This question only has a single sentence of description, which is "I am looking to add support for Jules Pattern Build in Android so I am looking for the tech primer or sample yaml file who can help me to achieve setting up pattern build." As you can tell from the lack of description, it is unclear what this person really is asking for. What kind of app are they integrating it into? Have they even started or have clear goals for what they are going to use Google Jules for?

This question clearly lacks many hallmarks of a smart question, as the title is very vague, the description is not very detailed and unclear, and shows minimal thought behind the question before asking it on StackOverflow. As a result, StackOverflow closed the question due to it needing more information and it also received 5 downvotes, indicating that the users of StackOverflow found this question not worthy of answering as well. While asking a smart question can seem obvious, examples like these show that many people need to think about how they ask questions to get a clear and timely answer. To read the full thread for this question, [click here](https://stackoverflow.com/questions/80002198/android-jules-pattern-build).

## What I Learned From These Questions

From these examples, it is clear that asking a smart question takes time and effort, but can pay you back in the form of a clear and thorough answer compared to no answer at all. I think that the main thing to remember when asking a smart question is to remember that most people aren't mind readers, and are going to need a clear explanation of the problem you are facing and enough context to know the solution. Overall, through learning about how to ask smart questions and looking at examples of smart and not-so-smart questions has underscored to me the importance of framing your questions to help other people to be able to and want to answer the questions I have, whether it be about software engineering or just about any other topic.  
