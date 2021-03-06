# DevCoder - Wit.ai
## Introduction
<b>Hi,</b> In this tutorial, I am going to teach you how to use <b>Wit.ai</b> through a fun mini project. By the end of this project, you will understand the basics of  <i>Natural Language Processing, intent recognition and entity extraction. You will also learn how to use wit.ai for your use cases.</i>

## Prerequisites
<ul>
  <li>No technical expertise needed (beginner friendly).</li>
  <li>Basic idea of Python and API calls (Optional).</li>
<li>Requires Python with version > 3 and streamlit library (Steps to download mentioned in the tutorial).</li></ul>

## Getting Started 
Ok, so let us consider a real world example to get ourselves excited :exclamation:. How do big companies like <i>Amazon, Flipkart</i> evaluate the customer reviews for a product or automate a considerable amount of  their customer care services? This is done with the help of Natural Language Processing (abbreviated as NLP). It is a branch of <i>Artificial Intelligence/ Machine Learning</i> that deals with the interaction between computers and humans through the medium of natural language. This could be <i>text or speech.</i> We ultimately want to derive meaningful insights from the end user’s input.

## Basic Concepts
Now, let us learn about 2 important concepts in NLP which will help us in implementing the project that follows this theory.
First, let us understand what <b>intent recognition</b> is. As the name suggests, we expect the computer to infer the intent from user’s input (text or audio) , understand the purpose of the message and thereby take meaningful actions.

<i>Example of this in everyday life:</i> When you ask Siri or google assistant to <i>set a reminder to wake you up in the morning</i>, it doesn’t call your most frequented contact which is totally irrelevant from our intended action. This is because it rightly understands what you wanted it to do and hence, does the same.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/voice-control-2598422_1280.jpg)
<i> Creative Commons License

<b><ins>Formal definition of Intent Classification</ins></b>:<br>
Intent classification is the automated association of text to a specific purpose or goal. In essence, a classifier analyzes pieces of text and categorizes them into intents such as Purchase, Downgrade, Unsubscribe, and Demo Request.<br>
<i>source: google</i>

Now, let us move on to what <b>entity extraction</b> is…. Continuing with the theme of the above voice assistant example, the term <i>'morning'</i> in your request <b><i>“Set a reminder to wake me up in the morning”</b></i> is somewhat vague. 

A more meaningful input to the device would be, <b><i>“Wake me up every day at 7 am”</b></i>. Now, your assistant wakes you up daily exactly at 7 am because not only did it recognize the intent of the user but it also extracted the entity. In this case, the assistant understands that the value ‘7’ refers to the time.

Note that people who built this algorithm had to define numbers like this to be extracted as 'time' before-hand and trained the AI algorithm accordingly.

<b><ins>Formal definition of Entity Recognition is</ins>:</b><br>
Named-entity recognition is a subtask of information extraction that seeks to locate and classify named entities mentioned in unstructured text into pre-defined categories such as person names, organizations, locations, medical codes, time expressions.<br>
<i>source: google</i>

## Basics of Streamlit
#### What is Streamlit?<br>
<i>Streamlit</i> is an open source web framework that lets you build webpages using only Python :snake:. Thereby, removing the need for developers to use HTML, CSS and Js. It uses what is called as widgets/components to construct your website.<br><br>
<b><ins>Developer Trivia</ins>:</b> Streamlit components are essentially Python wrappers of React code (Judges, extra points :grin:?).

#### Installing streamlit
~~~
pip install streamlit
~~~

#### Write some streamlit code
<img src="https://github.com/Sharan-Babu/FB_wit/blob/master/images/s_basics.png">

#### Running streamlit files<br>
Let us assume our file name to be 'streamlit_basics.py' and that we are in the correct directory.
~~~
streamlit run streamlit_basics.py
~~~

#### Output Website
Streamlit code is very intuitive and thus, you can understand the purpose of each widget by simply comparing the code to the rendered webpage.<br><br> For Example: You can place 'Title'/large text on the webpage by passing a string of your choice to the .title() method.<br> You can learn more about Streamlit here:
https://www.streamlit.io/<br><br>
<img src="https://github.com/Sharan-Babu/FB_wit/blob/master/images/sb.JPG">

:swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer:  :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer:  :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer:  :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: :swimmer: 
## What will we be building?<br>
We will be building a <b>'Code Editor Assistant'</b> (chatbot) with the help of <i>Python</i> and <i>Wit.ai</i> to help developers build cool software fast (No heavy code,I promise).

<img src="https://github.com/Sharan-Babu/FB_wit/blob/master/images/virtual-assistant.png" width="450" height="400"><br>
<i>Source</i>: <a href="https://iconscout.com/illustrations/virtual-assistant" target="_blank">Virtual-assistant Illustration</a> by <a href="https://iconscout.com/contributors/delesign" target="_blank">Delesign Graphics</a> (Creative Commons License)<br>

You can interact with the final outcome of this project by visiting the following URL:<br> https://share.streamlit.io/sharan-babu/fb_wit/Devbot.py

## Wit

<b>Wit.ai</b> is a <b>Facebook</b> owned open source chatbot framework with <i>advanced natural language processing</i> capabilities. The best part being you won’t have to code to train the NLP model (chatbot) or need prior knowledge of any kind. All you have to do is <i>type and click</i> and your chatbot is ready to be served in your app with the help of a simple API call.

Something that might interest you from a production/business perspective is that <b>Wit.ai</b> provides a <b>generous free tier</b> with up to <i>240 requests per minute per user</i> and <i>60 requests per minute per app</i>.

Now, let us build the <b>chatbot</b> from ground up using <i>Wit.ai</i> and I will be explaining the procedure one step at a time.


1) Go to the URL https://wit.ai/

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit1.JPG)

2)	Click on Continue with Facebook account and fill the necessary details.

3) Your homepage should look something like this. If this is the first time you have logged in, you will also be guided with the help of an interactive tutorial. Nevertheless, you can continue reading through this tutorial to navigate your way through the platform.
Now, click on the <b>Create New App</b> button.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit2.JPG)

4)	Select the <b>name</b> for your app and <b>preferred language</b> and click <b>'Create'</b>.
![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/create.JPG)

5)	A new project will be created and your screen should look like this:
<br><i>(Click on image to enlarge it)</i>
![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit3.JPG)

6)	To the <i>left</i>, you can find a handy menu bar which we will talk about in a minute and at the centre, you can see the main components with which we will be brewing our magic.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/leftbar.JPG)

7)	 Now, let us understand how to create an intent and select present entities in the incoming prompt as per our use-case <i>(Code Assistant)</i>.

8)	 In the <i>Utterance text field</i>, type what you think the end user might type. For example: A coder using our web app might type <i>"arrange my list called 'elements' in ascending order"</i>. So, this becomes our <b>utterance</b>. 

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/utterance.JPG)

9)	 Select the <b>‘Choose or add intent’</b> dropdown button. Now, enter an intent name (a name you are comfortable with) in the text field visible and click the <b>‘+ Create Intent’</b> button to the right. In this case, I will be naming my intent <b><i>‘arrange_list’</i></b>.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/addintent.JPG)

10)	<ins>Time to select an entity</ins>:
Select the text <b>‘elements’</b>. As soon as you do this, you will see a new dropdown menu. Now enter an entity name of your choice in the <b>‘Entity for elements’</b> text field and click <b>‘+ Create Entity’</b>. I will be naming it <b>‘list_name’</b>. I would recommend you to follow this naming convention if you are making the app along with me.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit4.JPG)

You can now see that wit.ai has highlighted our entity. 

11)	Click on the <b>Train and Validate</b> button at the bottom and <i>voila,</i> you just added the first utterance to your chatbot. :clap: :clap: :clap:

12)	From what we have done so far, we can realize the role that the extracted intent and entity will be playing in the website's source code. For example, considering the utterance we just added, it is important to know what the user had named his/her <i>'list'</i> as and what he/she wishes to do with it. With this information, we could return <b>‘elements = elements.sorted()’</b> to the user which is the right syntax for sorting elements in ascending order in Python.

13)	In the same way, you can add multiple utterances with corresponding intent and entities to the chatbot. The more the better. Add a considerable amount of utterances for the trained model to be well generalized. Only then will it return correct outputs for the user’s input prompt. Try to think from the user’s perspective and add your utterances.

14)	Do not forget to hit the <b>'Train and Validate'</b> button after adding each utterance!!!

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/train.JPG)

15)	One useful thing you might notice while working with <b>Wit.ai</b> is that after you add a few examples for a specific intent, Wit automatically tries to classify it. 

16)	After the end of this project, I would consider adding some other intents like <b>‘create_list’</b> , <b>‘list_reverse’</b> and <b>‘list_max’</b> and the names are self-explanatory as to what they mean.

17)	After you are done adding all your utterances to the chatbot, click on the Setting button under the <i>Management section</i> in the <i>Left menu bar</i>.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/settings.JPG)

18)	Therein lies an important piece of information which is the <b>Server Access token</b>. Copy this as we will be needing it later.

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/wit5.JPG)

That’s it. Our chatbot/ NLP agent is ready. Now, let us make a simple web interface for our <i>code editor assistant</i>.

## Code
If you wish to directly run the final program on your local machine,follow the instructions in the image below:<br><br>
![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/steps_to_run.png)
<br><br>

<b>(OR)</b> follow these steps and code along with me :muscle:.....

19)	Install required libraries

~~~
pip install streamlit wit streamlit-ace 
~~~
'<i>wit</i>' is the library to be installed for interacting with the Wit API and '<i>streamlit-ace'</i> library is to be installed to construct out of the box code-editors on the webpage as implementing one on our own can get quite complicated.

20)	Create a new python file called <b>Devbot.py</b> and paste the following code:<br>
<i>Read the comments in green to understand the code or follow along for an in-depth explanation of the code.</i>

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/code1.png)

You can find the above code at the following Github repo link:<br>
https://github.com/Sharan-Babu/FB_wit
<br><br>


21)	Here,you have one change to be made. At 'line 7' replace my 'access token' with yours which you copied from the settings page for the changes you made to take effect. You can use mine as well.
![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/token.JPG)

<b><ins>In-depth explanation of the code</ins></b>: <br><ul>
<li>We import the streamlit library as <i>'st'</i> and you can see that this is used multiple times, using which we construct widgets like input box, menu bars and buttons.</li>
<li> Other libraries to import are Wit and streamlit-ace (out of the box code editor).</li>
<li> In lines 6-10, we initialize variables for easy readability. Line 8 connects us to the <i>Wit chatbot</i>.</li>
<li> Lines 12-15 are completely optional. They are parameters of the streamlit-ace component. With this, you can change the supported languages, theme and feel of the editor among many other options.</li>
<li>The 'output' function from lines 18-23 take the intent and entity extracted from the returned JSON(JavaScript Object Notation) as input and map them to the corresponding outputs. Later, if you decide to add other intents and range of use-cases then all you have to do is write a case/if-block for handling those intents and entities.</li>
<li> Lines 24-40, we layout the widgets as per our choice on the webpage. As you can see, the streamlit-ace component has multiple changeable parameters like height,keybinding,font-size and tab-size among other things and they are all optional.
<li> Lines 44-57, we take input from the user with the help of a textfield, pass it to Wit and retrieve the JSON (similar to a <i>dictionary</i> in Python). The returned JSON looks like this:</li> </ul>

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/returned_json.JPG)

<ul>
<li> Line 48 and line 49 parse through the returned JSON and extract the intent and entity respectively. We wrap the entire block of code in a <i>'try...except'</i> block to handle errors.</li>
<li>Save the file. Open the terminal, go to the working directory and run the command:</li></ul>

~~~
streamlit run Devbot.py
~~~

</ul>

### <ins>Picture of the final web application</ins>:

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/image.JPG)

If you instead want the simplest interface possible, you can use the following code and have a look at the resulting webpage (Compared to the previous code, we have simply replaced the code editor component with a text-field. Nothing else has been done).

![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/simpler_website.png)

### Output:
![''](https://github.com/Sharan-Babu/FB_wit/blob/master/images/simple_code_website.JPG)

That’s it. We are done and now you have a fully functional and useful web app that can help make the lives of <i>devs</i> a little bit easier. <i>Congrats on making your first chatbot with Wit.ai and successfully integrating it with a web application. I would recommend you to make this app more robust or make other useful apps with your newly learnt skills!</i>:dancer: :dancer:

<br><br>
Scroll to the end to read about my experience with Wit and participating in this competition :point_down:
<hr>

### Other Links
Youtube URL for the demo: https://youtu.be/OQjbIcpCgSE
<br>
Github repository link: https://github.com/Sharan-Babu/FB_wit
<br>
Hosted Website Link: https://share.streamlit.io/sharan-babu/fb_wit/Devbot.py
<br><br>
Please feel free to give your feedback @:<br>
Email: sharanbabu2001@gmail.com  <br>
Linkedin: https://www.linkedin.com/in/sharan-babu-39a757197/
<hr>


## Personal Experience
It all started with this <a href="https://fbai3.devpost.com/">Facebook Hackathon</a>(2 months ago) as this was the first time I learnt Wit by reading the official documentation and accompanying videos. I experimented with various projects and finally decided on a voice application. Unfortunately, I could not win in that hackathon but learnt a lot about Wit and its features. Later, apart from the pleasant swags I received from <i>Facebook</i> for a successful submission, I was also invited to participate in a Week long Wit.ai JAM session. This was really wonderful for multiple reasons. I got to meet cool people who were using Wit in ways I had never imagined and this was the first time I was part of a professional community of devs :smile:. Apart from that, we had daily sessions ranging from Lightning talks to Natural Language Understanding (NLU) which were all very insightful. Later, I was super stoked to learn that I had been selected as one of the 21 regional winners and was on :cloud:9 . The tutorial you just read was updated with the feedback I received after the first round in mind. I hope you enjoyed reading it and had something to take away. <br><br>
From a technical perspective, I like <i>Wit.ai</i> for NLP tasks more than its rivals like Dialogflow or Rasa. 
<br><br>
To conclude, I would like to say that <i>Wit</i> has a special place in my heart among other technical skills and am glad that I could contribute to the community. I intend to write more tutorials on Wit.ai and help people learn to use this amazing chatbot framework.

Cheers!
