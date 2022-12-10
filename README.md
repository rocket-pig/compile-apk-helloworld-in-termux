# compile-apk-helloworld-in-termux
Go from zero to APK with tools available from apt in termux.  No gradle, no maven, no IDE just CLI. 


This took me over 100 hours to accomplish.  I am no Java expert, nor at this point do I want to be.  It is exceedingly unlikely that this will instantly work for you, without some more cryptic compilation error and fucking with environment vars and wondering why the whole chaotic tangled mess is so obscenely FRAGILE.

Anyways the bones are there to make whatever without needing the (bare minimum!) 4GB of bloat.

I had begun intending to get to WebView, and then switch to creating in javascript..a poor man's 'flutter' or 'cordova' etc.  I didnt want some multi-GB manager software over my head.  And I see now why they exist, without them y're guessing in the dark why the underlying tools hate eachother.

Yep, I'll stick with developing things in javascript and python...you essentially get the same
"write once run everywhere" virtual machine situation, and they don't hate your guts for trying to use them

SO:

##TO USE##
You'll need to source an android.jar, there's every flavor available here:

Then, `apt install aapt2 dx zip openjdk-17`

The build script runs from outside the project folder:
`./build.sh helloworld/` _in_theory_ would be it, but my money's on it taking some pounds of flesh from you too before you see "Install this now?" and Google's idiotic warnings that they didnt approve of your 30KB homebrew app

