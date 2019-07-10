# DailyPharses-English-To-Hindi

## Creating a Phrases Translator for English to Hindi Translation

In the below blog tutorial, we're going to build an application which will play 8 different phrases. The phrases are daily use terms and sentences in English language, translated to Hindi language(audio) on tapping the respective phrase.

Assumptions: 
1. knows how to set up Id for elements
2. Have audio files or be able to create using tools such as audacity

### Step 1:
First, launch the Android Studio and open a new project with an empty activity. Once the gradle build finishes, continue with setting up the layout of the application. <br>
An empty project by default has a TextView set up within a Constraint Layout. So, go ahead and delete the Text View and pull in a grid view on top of the existing constraint layout. For the grid, add the rowCount and columnCount attributes of layout, as 4 and 2 respectively.<br>
These counts can be anything you want. We are using a 4X2 layout, as we want our application to have 8 buttons, which will play 8 different phrases. 


### Step 2:
Now for each of the grid cell, add a *Button*. One for each cell of the grid. So, go ahead and start placing Buttons for each of the cells.<br>
Add `onClick` function to each of the buttons `android:onClick="playPhrase"`. 


### Step 3: 
For our application we are using 8 prompts:
- Hello 
- How are you?
- Please meet me sometime.
- Shall we meet tomorrow?
- Where are we?
- What are we doing?
- What time is it?
- Yesterday, Today, Tomorrow

For playing these prompts, we are going to place the audio files for the phrases in `res/raw` folder of the app.
And the audio files should be named, same as the tag values for buttons. You can select different names as well, but that will complicate the process unnecessarily.
Add these tags to each one of the buttons places created in the grid at *Step 2*.

`android:tag="hello"`

`android:tag="howareyou"`

`android:tag="pleasemeet"`

`android:tag="meettomorrow"`

`android:tag="wherearewe"`

`android:tag="whatarewedoing`

`android:tag="whattimeisit"`

`android:tag="yesterdaytoday"`

### Step 4: 
Now let us add the `playPhrase` method to `MainActivity.java` file.

The function takes in `View` as a parameter. We declare a Button variable, `buttonPressed` to capture the tag value from the variable.
Then we declare a MediaPlayer variable, `mediaPlayer` and then we call `create()` method of MediaPlayer class on the `mediaPlayer` object.<br>
We then pass, context and the resource to be played, as parameters to the method.<br>
After this configuration is completed, we just need to call `start()` method on `mediaPlayer`. And we are good to go.

```
 public void playPhrase(View view){
        Button buttonPressed = (Button) view;
        MediaPlayer mediaPlayer = MediaPlayer.create(this, getResources().getIdentifier(buttonPressed.getTag().toString(), "raw", getPackageName()));
        mediaPlayer.start();
    }
```

This completes the application as we wanted it to work and we are now good to go for packaging the program into an **".apk"** file.

*Keep coding! Have fun.*

The full code of the application is available at GitHub:
[Github/The-Cyberian](https://github.com/TheCyberian)
