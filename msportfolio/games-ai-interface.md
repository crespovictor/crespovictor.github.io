---
title: From games to AI
author: Victor Crespo
date:
layout: post
permalink: "/portfolio/masters-s2-portolio/games-ai-interface"
---

## Implementation of a "Guess Who" board game using a decission tree clasifier
### A Google Colab Notebook for this skill is here.

This work is based on the Guess Who card game. Guess who is a board and card game where one players tries to guess who is the selected character of the other player. They ask questions that can be answered with Yes or No only regarding physical characteristics of the characters. The players, then, start to discriminate the characters based on the answers that were provided to them, until they can make a guess of the other player's character. The first person to guess who their opponent's character is wins the game.

For this experiment, a series of features was manually extracted from the cards to define characteristics of the people present in the cards. Such features or characteristics will allow us to predict who is the character that the user is thinking of, or holding the card of.

We avoided using gender and age to classify the characteres, and relied on physical characteristics to perform the prediction. The main reason to avoid gender and age is because these features can be seen as an spectrum rather than a binary aspect, and we feared that by refering to them as binary we could lead to bias by gender or age (i.e., is not easy to say when a person is considered old or young, etc)

The characteristics and their related questions are:

- "hair_short":"Does your character have short hair? (If your character doesn't have hair, answer N)",
- "facial_hair":"Does your character have facial hair?",
- "head_covered":"Does your character have their head covered? (Cap, hat, veil, beanie, etc)",
- "brown_eyes":"Does your character have brown eyes?",
- "has_glasses":"Does your character wear glasses?",
- "dark_hair":"Does your character have dark hair? (Not blonde, red, or white. If their hair seems dyed but is dark, - answer Y)",
- "has_hair":"Does your character have hair?",
- "blue_eyes":"Does your character have blue eyes?",
- "green_eyes":"Does your character have green eyes?",
- "dyed_hair":"Does your character have dyed hair?",
- "curly_hair": "Does your character have curly hair?"  
By using these features, the model is able to predict who is the player's character.

## Intent of this work
While doing the Decission Tree Classifier Homework based on the Zoo Database and the ANU Coffee database experiments we did in the Course CECS8001, and while doing a visual exploration of the tree, I couldn't help but think of it as a Guess Who game. With this experiment, I hope to provide a way to explain Decission Tree Classifier to an audience that might not be entirely aware of Machine Learning methods and/or terminology.

## Limitations
Each character has its own label, meaning that there are 20 differente labels for 20 data points or entries in the dataframe. In practice, this means that the model is overfitted to the characters. Since there are not characters that we can test the model on, and since trying to guess for non-existings characters breaks the rules of Guess Who, testing the model is out of the scope of this experiment.

## Example of usage
We will use Joe to exemplify the usage of the trained model  
<img src='/assets/img/Joe.jpg' class='w-50'>  
and answering the questions for him:
```
"Does your character have short hair? (If your character doesn't have hair, answer N)" => No
"Does your character have facial hair?" => Yes
"Does your character have their head covered? (Cap, hat, veil, beanie, etc)" => No
"Does your character have brown eyes?" => No
"Does your character wear glasses?" => Yes
"Does your character have dark hair? (Not blonde, red, or white. If their hair seems dyed but is dark, answer Y)" => No
"Does your character have hair?" => No
Does your character have blue eyes?" => Yes
"Does your character have green eyes?" => No
"Does your character have dyed hair?" => No
"Does your character have curly hair?" => No
```
After answering these questions in Google Colab, we get a prediction:
```
Answer these questions and we might be able to find who your character is.
Only answer Y or N
Does your character have short hair? (If your character doesn't have hair, answer N)N
Does your character have facial hair?Y
Does your character have their head covered? (Cap, hat, veil, beanie, etc)N
Does your character have brown eyes?N
Does your character wear glasses?Y
Does your character have dark hair? (Not blonde, red, or white. If their hair seems dyed but is dark, answer Y)N
Does your character have hair?N
Does your character have blue eyes?Y
Does your character have green eyes?N
Does your character have dyed hair?N
Does your character have curly hair?N
Your character is: Joe
```
All the characters' cards are in [this folder][img_folder], so you can try them all.

The process that the algorithm follows can be described using this diagram:
<a href='/assets/img/decisiontree.png' target='_blank'><img src='/assets/img/decisiontree.png' class='w-75'></a>  
Click on the image to make it larger

## Conclusions
Decision Tree Models are one of the most easy and simple machine learning models. However, since they are _machine learning models_, they can be intimidating to certain people with no knowledge of either computers, machine learning or technology at all. In this work, we explored a way of interfacing with a very simple machine learning model using a well known board game. Although the model is overfitted, and using it out of its boundaries can lead to the model not working as expected, is still useful to visualize the way decision trees make decisions. The visualization, taken from the CECS8001 ANU Coffee/Zoo ML homework, is hard to understand if no previous knowledge of either the dataset or the model. This is why, in order to improve the understandability of it, I created an anotated version of the decision tree diagram. It shows the _questions_ that were asked by the model to predict who was the player's character.

Tools like this exercise can help to improve the explainability and understandability of simple ML models.

## How this can improve:
- Graphical User Interface: Considering that the main intention of this experiment is to introduce people with limited knowledge of machine learning to how a model work, using the command line could be intimidating to some people
- Understand the limitations of the model: We acknowledge that this model is overfitted, and should be used within those limitations. The model classify characters and not people. Users should be aware of those limitations.
- Use other games: While this is a simple example of how a decision tree works, it would be useful to think of videogames as a way of interfacing with ML models. Rather than using ML and/or AI in games and videogames, classical games (board games) can be used to understand the way models work.
- Use similar tools to teach ML. The main intent of this experiment was to explore a familiar way (using a well known board game) to understand how ML models make decisions, and change the idea of AI/ML as a black box. It would be really useful to see this kind of experiments on the field, to guide kids and other people into Machine Learning.

[img_folder]: https://drive.google.com/drive/folders/1VeNs-tGSyv9uOiQ9RuJfnJw-pxfmRwA8?usp=sharing