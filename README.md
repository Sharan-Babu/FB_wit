# DevCoder - Wit.ai
Hi. In this tutorial, I am going to teach you how to use wit.ai through a fun mini project. By the end of this project you will understand the basics of  Natural Language Processing, intent recognition and entity extraction.

Ok, so let us consider a real world example to get ourselves excited. How do big companies like Amazon, Flipkart evaluate the customer reviews for a product or automate a considerable amount of  their customer care services? This is done with the help of Natural Language Processing (abbreviated as NLP). It is a branch of Artificial Intelligence/ Machine Learning that deals with the interaction between computers and humans through the medium of natural language. This could be text or speech. We ultimately want to derive meaningful insights from the end user’s input.

Now, let us learn about 2 important concepts in NLP which will help us in implementing the project that follows this theory.
First, let us understand what intent recognition is. As the name suggests, we expect the computer to infer the intent from user’s input (text or audio) , understand the purpose of the message and thereby take meaningful actions.

Example of this in everyday life: When you ask Siri or google assistant to set a reminder to wake you up in the morning, it doesn’t call your most frequented contactwhich is totally irrelevant. This is because it rightly understands what you wanted it to do and hence does the same.

A formal definition for what intent classification is:
Intent classification is the automated association of text to a specific purpose or goal. In essence, a classifier analyzes pieces of text and categorizes them into intents such as Purchase, Downgrade, Unsubscribe, and Demo Request.
‘’’
source: google

Now, let us move on to what entity extraction is…. Going with the setting of the above voice assistant example, the term morning in your request “Set a reminder to wake me up in the morning” is very vague. 

A more meaningful input to the device would be, “Wake me up every day at 7 am”. Now, your assistant wakes you up daily exactly at 7 am because not only did it recognize the intent of the user but it also extracted the entity. In this case the assistant understands that the value ‘7’ refers to the time.

Note that people who built this algorithm had to define numbers like this to be extracted as time before hand and trained the AI algorithm accordingly.

A formal definition for what entity recognition is:
Named-entity recognition is a subtask of information extraction that seeks to locate and classify named entities mentioned in unstructured text into pre-defined categories such as person names, organizations, locations, medical codes, time expressions
‘’’source: google

What will we be building?
We will be building a code editor assistant with the help of python and wit.ai to help developers build cool software fast ( No heavy code,I promise).

You can interact with the final outcome of this project by visiting the following URL: https://share.streamlit.io/sharan-babu/fb_wit/Devbot.py

Wit.ai is a Facebook owned open source chatbot framework with advanced natural language processing capabilities. The best part being you won’t have to code anything or need prior knowledge of any kind to build chatbots. All you have to do is type and click and your chatbot is ready to be served in your app with the help of only a simple API call.

Something that might interest you from a production perspective is that wit.ai provides generous free tier with up to 240 requests per minute per user and 60 requests per minute per app.

Now, let us build the chatbot from ground up using wit.ai and I will be explaining it one step at a time.


1) Go to URL https://wit.ai/

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit1.JPG)

2)	Click on Continue with Facebook account and fill the necessary details.

3) Your homepage should look something like this. If this is the first time you have logged in, you will also be guided with the help of an interactive tutorial. Nevertheless, you can continue reading through this article to navigate your way through the platform.
Now, click on the Create New App button.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit2.JPG)

4)	Select the name for your app and preferred language and click create.

5)	A new project will be created and your screen should look like this:
![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit3.JPG)

6)	To the left you can find a handy menu bar which we will talk about in a minute and in the center you will see the main components with which we will be brewing our magic.

7)	 Now, let us understand how to create an intent and select present entities in it as per our case (voice code assistant)

8)	 In the Utterance text field, type what you think the end user might say. For example: A coder in our case might say arrange my list called elements in ascending order. So, this becomes our utterance. 

9)	 Select the  ‘Choose or add intent’ dropdown button. Now, enter a intent name (whichever you are comfortable with) in the text field visible and click the ‘+ Create Intent’ button to the right. In this case, I will be naming my intent ‘arrange_list’

10)	Time to select a intent:
Select the text ‘elements’. As soon as you do this, you will see a new dropdown menu. Now enter an entity name of your choice in the ‘Entity for elements’ text field and click ‘+ Create Entity’. I will be naming it ‘list_name’. I would recommend you to follow this naming convention if you are making the app along with me.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit4.JPG)
You can now see that wit.ai has highlighted our entity. 

11)	Click on the Train and Validate button at the bottom and voila you just added the first utterance to your chatbot.

12)	From what we have done so far, we can realize the role the extracted intent and entity will be playing in the long run. For example, considering the utterance we just added, it is important to know what the user had named his/her list as and what he/she wishes to do with it. With this information, we could return ‘elements = slements.sorted()’ to the user which is the right answer for sorting elements in ascending order in Python.

13)	This way add multiple utterances with corresponding intent and entities to the chatbot. The more the better. Add a considerable amount of utterances for the to be trained model to be well generalized. Only then will it return correct outputs for the user’s input prompt. Try to think from the user’s perspective and add your utterances.

14)	( Do not forget to hit the Train and Validate button after adding each utterance!)

15)	One useful thing you might notice while working with wit.ai is that after you add a few examples for a specific intent, wit automatically tries to classify it. 

16)	I would consider adding some other intent like ‘create_list’ , ‘list_reverse’ and ‘list_max’ for the purpose of this demo and the names are self-explanatory as to what they mean.

17)	After you are done adding all your utterances to the chatbot, click on the Setting button under the Management section in the Left menu bar.

18)	Therein lies an important piece of information which is the Server Access token. Copy this as we will be needing it later.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit5.JPG)

That’s it. Our chatbot is ready. Now let us make a simple web interface for our voice based code assistant.

19)	Create a new python file called Devbot.py and paste the following code:

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/steps_to_run.png)

You can find the code and steps to run the program at the following Github repository:
https://github.com/Sharan-Babu/FB_wit

20)	Clone the repo. Install required libraries and open Fb_Ai.py

21)	Here you have a few changes to be made. At line 7 replace my access token with yours you copied from the settings page for app to work.

22)	I have built the web interface along with the interactive code editor you can see using a Python web framework called streamlit. You can learn more about it here: https://www.streamlit.io/

23)	Lines 20 to 34 is the backend function that takes the intent extracted as the input . Wit API returns JSON (Javasript Object Notation). It is similar to a Python dictionary and from that we can find the returned entity. Using this we can hand-craft the output to be displayed to our user.

24)	That’s it. We are done and you have a fully functional and useful web app that can help make the lives of devs a little bit easier. Go enjoy!

25)	Youtube URL for the demo: https://youtu.be/OQjbIcpCgSE




