# FirstGameTest

### Introduction

This is a study of game creation in Android, using only the raw libraries, without any support of an sdk.
I am using the following tutorial for the initial study:

https://www.simplifiedcoding.net/android-game-development-tutorial-1/
https://www.simplifiedcoding.net/android-game-development-tutorial-2/

Since the tutorial is already explained and detailed, I will only cover some basic information and some further discussions where it lacked any details of why and/or how it was done.

Let´s begin with the downloads needed to start everything.
- Android IDE

https://developer.android.com/studio/install.html

Make sure you also download the SDK and configure the AVD manager (since genymotion is paid now... shame on you genymotion).

- Git (for windows)

https://git-scm.com/download/win

Yes, for windows...

This will be enough for you to run and test the application.

### First steps

There aren't many things different from importing the resources and changing the base style, but one thing that I have never searched in detail was the:

```sh
xmlns:tools="http://schemas.android.com/tool"
```

Basically, it allows you to add tools attributes in your XML. The entire list of attributes can be found in:

https://developer.android.com/studio/write/tool-attributes.html

Skipping to the first part of the source code, the main activity uses a function called:

```
setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE);
```

https://developer.android.com/reference/android/app/Activity.html#setRequestedOrientation(int)

Interesting way to make the screen rotates rather than forcing it by the layout.
One thing that must be remembered:

> If the activity is currently in the foreground or otherwise impacting the screen orientation, the screen will immediately be changed (possibly causing the activity to be restarted)

If the activity is restarted, then we should not forget to handle it.

### Building the game view