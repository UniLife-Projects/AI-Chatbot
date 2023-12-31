# Hudson's Drip™ customer service AI Chatbot

We developed an AI-driven chatbot for our online apparel store, Hudson's Drip, employing agile SDLC practices and executing the project in two scrum phases.

The chatbot operates on two JSON files that train a neural network to tailor responses based on customer details. The `training.py` file, drawing data from `intents.py`, educates the neural network. Post-training, it generates 'words' and 'classes' pk1 files, which `predict.py` uses to evaluate the likelihood of a user query relating to a specific subject in `intents.JSON`. The chatbot then selects a suitable reply from the most probable topic. Additionally, it's equipped to sense and adapt to the user's emotional tone in its responses.

For development, we utilized various libraries including tkinter, random, json, pickle, numpy, nltk (featuring Porterstemmer, WordNet Lemmatizer, and Sentiment Intensity Analyzer), and TensorFlow.


[JIRA Roadmap](https://durvan.atlassian.net/jira/software/projects/CT3/boards/).  
[Reference material](https://www.youtube.com/watch?v=1lwddP0KUEg). 
  
## COSC 310 Group members:
- Guiherme Durvan António Zandamela
- Lakshay Karnwal
- Abdulaziz Almutlaq
- Ravil Bigvava
- Jordan onwuvuche

### Individual Project tasks:

For the individual project, I utilized two public APIs: Google translate API and Flickr API. Implementing these two APIs increased the functionality of my chatbot. I have explained the use of the two APIs below.

#### Google Translate API
![GUI Screenshot](https://user-images.githubusercontent.com/60047109/162899488-91d0aedf-2d1d-4fab-9a58-887d6ce67a45.png)

The translate API is used to add three different language options for the users. Since, Hudson's drip customer service chatbot is going to be used in Canada, I have included the option for users to choose among the top three languages spoken in Canda. The three language options are: English, French and Chinese (since mandarin is not provided by google translate).

When the chatbot starts, the user is asked to choose their language of choice. After the user makes their selection the conversation proceeds in that selected language. For the implementation details check the API_implementation file.

#### Flickr API

The Flickr API is well known for its image and caption datasets. I decided to use this api to include media in the chatbot. Using the Flickr api I was able to scrape images of cute pets from their online dataset. Then, I used these images to be displayed whenever the user was extremely frustrated during the conversation. It is always helpful to make a person smile, when they are not feeling the best :)

![GUI Screenshot](https://user-images.githubusercontent.com/60047109/162899014-b0bc8899-d1f9-4a3c-a8c5-fda75e9e807b.png)

For the implementation details check the API_implementation file.

![GUI Screenshot](https://user-images.githubusercontent.com/60047109/162911260-c51095f1-68f5-40c3-8e9d-343de079c232.jpeg)

This is the cute pet image that shows up.


### Assignment 3 tasks:

#### GUI Implementation
![GUI Screenshot](https://raw.githubusercontent.com/durvanZ/COSC310_Team3/main/screenshots/botdemo.png)

The GUI was implemented using the Python tkinter module for graphical interfaces. Using this module we created a text box where the user enters their query/text. This helps the app become intuitivey easy-to-use for the user.

#### Test cases implementation

The Automated Unit Testing Framework used for this was pytest due to its easy to use module functions. We created multiple test cases for all the important functions which checks if all the functions are working as desired. You can run the Unit testing file using the pytest command. After running the test file, pytest displays a summary of failed and passed functions. If the functions do not pass that means the chatbot will have errors, if all the functions pass that means the program is working as desired.

![Unit Testing Screenshot](https://user-images.githubusercontent.com/60047109/159101549-550633ec-41f7-408e-8fa5-5a43b64d2d75.png)

In the screenshot example above, one of the functions failed because the value of probability was not correct. This is a useful feature as it reduces effort to debug the code.

#### Sentiment analysis

We used a natural language toolkit "Sentiment intensity analyzer" to obtain positivity and negativity scores from the words in the user input. This information was used to make conditional statements in which the response of the bot is either complemented or replaced (depending on the intensity) by a response designed to address the sentiment of the user.

![Sentiment analysis demo](https://raw.githubusercontent.com/durvanZ/COSC310_Team3/main/screenshots/sentimentdemo.png)

#### Word stemming in ambiguous cases

Word stemming was used in addition to unstemmed input. Our algorithm stems the user input if the bot is not able to find a probable intent (probability > 0.50).
This helps to prevent inaccurate responses and can address suffixes.

![Sentiment analysis demo](https://raw.githubusercontent.com/durvanZ/COSC310_Team3/main/screenshots/sentimentdemo.png)
