# Module 0. Welcome, setup, and your first VLA

Welcome to the course. In the next thirty minutes you are going to:

1. Understand, in plain language, what a Vision-Language-Action model is.
2. Create a free Hugging Face account so you can download pretrained models.
3. Open a Google Colab notebook and run a real, pretrained VLA called **SmolVLA** from the Hugging Face LeRobot team.

You do not need to understand a single line of code yet. The point of this
module is simply to stand at the finish line before we walk back to the start.

## What is a Vision-Language-Action model?

A Vision-Language-Action model, or **VLA**, is a neural network that takes
two things as input:

1. What a robot sees, as one or more camera images.
2. A natural language instruction, like "pick up the red cube and place it in the box".

And it produces one thing as output:

1. The next few robot actions to take, as numbers that move the robot's joints or end effector.

That is it. A VLA is a function from (images, instruction) to (actions).

Here is the same idea as a diagram:

```{mermaid}
flowchart LR
    A[Camera images] --> C[Vision encoder]
    B[Natural language<br/>instruction] --> D[Language encoder]
    C --> E[Fusion]
    D --> E
    E --> F[Action decoder]
    F --> G[Robot actions<br/>joint angles, gripper, etc.]
    style G fill:#d1fae5,stroke:#10b981
```

Everything in this course is about understanding each box in that diagram,
and eventually building and training one yourself.

## Why this matters

Until very recently, robots were programmed for one task at a time. A pick
and place robot had no idea what to do if you moved the bin or changed the
object. VLAs change that. Because their language half is trained on huge
amounts of internet text and their vision half is trained on huge amounts
of internet images, a VLA can generalize to new objects, new tables, and
new instructions it has never seen. That is a very big deal, and it is
what this course is going to teach you to build.

## Your two tasks for this module

### Task 1. Create a free Hugging Face account

Hugging Face is where most open source AI models live, including every
single model we will use in this course. Creating an account takes one
minute and does not require a credit card.

1. Go to [huggingface.co/join](https://huggingface.co/join).
2. Sign up with your email. Pick a username you are happy with. It will
   appear on any model or dataset you publish later.
3. Verify your email.
4. When you are logged in, go to your profile, click **Settings**, then
   **Access Tokens**, then **Create new token**. Give it the name
   `vla-course`, set the type to **Read**, and click **Create token**.
5. Copy that token somewhere safe. You will paste it into Colab in a minute.
   You can always come back to the same page and create another token if
   you lose it.

### Task 2. Run the Hello VLA notebook

Click the little rocket icon at the top of the next page of this course
(the page called **Hello VLA**). Pick **Colab** from the menu. The notebook
will open in your browser.

Follow the instructions inside the notebook cell by cell. By the end you
will have:

1. Loaded a real multimodal model and asked it to describe an image in
   natural language.
2. Loaded the full SmolVLA model and confirmed its size (about 450 million
   parameters).
3. Seen, with your own eyes, that a pretrained VLA is not a mystical black
   box. It is a file you can download, load, and inspect.

## What to do if something breaks

The single most common thing that will break in any notebook in this course
is that a library has updated its API since the course was written. When
that happens:

1. Read the error message. Most of the time it tells you exactly what changed.
2. Search the error on the library's GitHub issues page.
3. If you are stuck, open an issue on this course's repo with the error
   and which lesson you were on, and we will fix the notebook.

Flaky Colab runtimes are the second most common issue. If a cell hangs for
more than two minutes on something that should be fast, click
**Runtime → Restart session** and run the cells again.

## What you will have at the end of Module 0

1. A Hugging Face account and access token.
2. A Colab notebook you ran yourself, end to end.
3. A working mental picture of the three parts of a VLA: vision, language, action.

When all of the above is true, move on to **Module 1**, where we start
building real intuition by coding with NumPy and plotting our first graphs.
