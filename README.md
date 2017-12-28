# simplebot

This is a really simple chatbot we created as final-year students in 2016, in a team of 2, by using AIML. It is hosted on Pandorabots (for free).
We were given a few hours and had to play around with AIML in order to show we were able to use its format (see "Scenario" down below for more explanation about it)

## Test

You can chat with this bot by going to https://playground.pandorabots.com/en/clubhouse/. Then type `sebranly_simple_bot` in the search bar and then click on "Talk" on the resulting chatbot.
See "Scenario" down below in order to learn how to interact with it as it's a simple showcase

## Installation

The Pandorabots Platform is "one of the oldest and largest chatbot hosting services in the world."

Here are the steps to follow in order to create a copy of this chatbot:
- Go to https://playground.pandorabots.com > `Log In` > `My Bots` > `Create Bot`
- Type a name for the chatbot and select `English` as the language
- Once the bot created, you can go to `Files` tab and delete some files:
	- under the AIML section: `udc`
	- under the Substitutions section: `denormal`, `gender`, `normal`, `person` and `person2`
		- Note: do not delete anything under the System section

Now, you can upload files you got from this git repository. More specifically, you can upload `pand_initial.aiml`, `colors.set`, `countriescapitals.map` and `normal.substitution` files.
Under the SYSTEM section on the interface, go to properties and add a key-value whose key is `age` with the value you want (e.g. `13`). Indeed, that's the only change I made to this file.
Go to `Train` tab and play around by typing something under "Human" and hit "Ask" to see the bot's reply

## Scenario

Here is a scenario you could witness by chatting with this bot. The goal here is to show that we, as developers, were able to use several several different AIML aspects

### Format for the examples:
```
i: this is what you should type with your keyboard (the input)
o: this is what the bot will reply (the output)
e: this is the reason why the bot replies this way (the explanation from an AIML perspective)
```

### Examples
```
i: guihfghuhfggfihi (basically, something meaningless)
o: I did not understand. (or something similar)
e: if the bot doesn't know what to reply, it gives a random answer stating it
```

```
i: Hello
o: Hello!
e: this is a simple example of pattern-matching
```

```
i: Hey
o: Hello!
e: the <srai></srai> tag enables to lead to the HELLO case
```

```
i: I am 22 years old
o: You're 22 years old!
e: uses <star /> tag to get the user age thanks to * symbol in the pattern
```

```
i: How old are you?
o: I'm 13 years old.
e: thanks to <bot name="age" /> tag it can fetch the bot age we defined as a property
```

```
i1: Say my name
o1: You didn't tell me yet, sorry.
e1: the bot is not able to reply as the user didn't tell him his name first

i2: My name is Sebastian and I'm 77 years old
o2: Oh right, your name is Sebastian and you are 77 years old!
e2: enables the bot to create a username variable with the value Sebastian

i3: Say my name
o3: Your name is Sebastian
e3: the bot is now able to reply as it got the information beforehand
Note: on Pandorabots, hitting "Reset Bot Memory" will erase this information and lead back to o1 instead of o3
```

```
i: What is the first word in house car rabbit
o: Pretty easy, it's house
e: uses <first> tag to get the first element of a list
```

```
i: Remove the first word from house car rabbit
o: Okay, here's what I get: car rabbit
e: uses <rest> tag to get everything but the first element of a list
```

```
i1: Is blue a color
o1: Yes, blue is indeed a color
e1: uses the set we defined in order to identify that such a word is a color

i2: Is car a color
o2: Nope, car is not a color
e2: uses the set we defined in order to identify that such a word is not a color 
```

```
i: What is the capital of France?
o: Paris is the capital of France
e: uses the map we defined in order to match a country to its capital
```

```
i: Let's talk about coffee
o: Do you like coffee?
then either
i1: Yes
o1: You're a great person!
or
i2: No
o2: You're not a real developer then. Or actually you take naps like sebranly instead.
e: uses <that> tag to memorize a topic context (e.g. coffee in this case)
```

```
i: Today is monday
o: The beginning of the week!
i: Today is friday
o: The weekend is getting closer!
i: Today is ufo
o: Hmm, it is not a valid day!
e: use conditions in order to behave like a switch(case) structure in C for example
```

```
i1: Is two even
o1: I did not understand. (or something similar)
i2: Two is even
o2: Oh nice, thanks for teaching me this!
i3: Is two even
o3: Yes it is! You just taught me that :)
e: thanks to <learn> tag, the bot learnt something new it can use
```

```
i: Rocket launch in 10
o: 1 2 3 4 5 6 7 8 9 10
i: Rocket launch in 3
o: 1 2 3
e: loop over thanks to a variable to change and display its value after each iteration
```

```
i: Who is sebranly
o: He's the author of this simple bot, well he made me ("author" is bold)
e: shows that we can use HTML tags to format the bot answer
```

```
i1: Can we talk about SpaceX?
o1: Sure!
i2: So, I want to know... (or anything else)
o2: Well, just kidding, I know you would like to learn more about SpaceX but I'm just a simple bot
e: shows that we can encapsulate the conversation into specific topics (sub-blocks of AIML)
```
