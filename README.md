# compile-apk-helloworld-in-termux
Go from zero to APK with tools available from apt in termux.  No gradle, no maven, no IDE just CLI.

  .--.      .-'.      .--.      .--.      .--.      .--.      .`-.      .--.
:::::.\::::::::.\::::::::.\::::::::.\::::::::.\::::::::.\::::::::.\::::::::.\
'      `--'      `.-'      `--'      `--'      `--'      `-.'      `--'      `

`git clone https://github.com/rocket-pig/compile-apk-helloworld-in-termux`,

`apt install aapt2 dx zip openjdk-17`,

`cd compile-apk-helloworld-in-termux`,

`./build.sh project/` 

...and the rest of this is just me huffing and puffing to nobody

  .--.      .-'.      .--.      .--.      .--.      .--.      .`-.      .--.
:::::.\::::::::.\::::::::.\::::::::.\::::::::.\::::::::.\::::::::.\::::::::.\
'      `--'      `.-'      `--'      `--'      `--'      `-.'      `--'      `


This took me over 100 hours to accomplish.  I am no Java expert, nor at this point do I want to be.  It is exceedingly unlikely that this will instantly work for you, without some more cryptic compilation error and fucking with environment vars and wondering why the whole chaotic tangled mess is so obscenely FRAGILE.

Anyways the bones are there to make whatever without needing the (bare minimum!) 4GB of bloat.

I had begun intending to get to WebView, and then switch to creating in javascript..a poor man's 'flutter' or 'cordova' etc.  I didnt want some multi-GB manager software over my head.  And I see now why they exist, without them y're guessing in the dark why the underlying tools hate eachother.

Yep, I'll stick with developing things in javascript and python...you essentially get the same
"write once run everywhere" virtual machine situation, and they don't hate your guts for trying to use them


___ ("""-.___ ("""-.___ ("""-.___ ("""-.___ ("""-.___ ("""-.___ ("""-.
 __) "")   __) "")   __) "")   __) "")   __) "")   __) "")   __) "")
(__,-""   (__,-""   (__,-""   (__,-""   (__,-""   (__,-""   (__,-""


SO:

The build script runs from outside the project folder:
`./build.sh helloworld/` _in_theory_ would be it, but my money's on it taking some pounds of flesh from you too before you see "Install this now?" and Google's idiotic warnings that they didnt approve of your 30KB homebrew app

I left the generated keystore in there for if the keysigner tool isnt around or doesnt work or whatever.  I also just copied over the `android.jar` and couple of tools from the bloated 90GB ball of shite that google has you download...everything to build /should/ be here aside from what termux's pkg manager has...

gluck! hae fun! dont ever call me again!

#### EXAMPLE LOG OUTPUT FOR FUNSIES ####

```
Work Dir: /data/data/com.termux/files/home/github-upload-dealy/project/
Directory exists, continuing...
---------------aapt2:
res/layout/activity_main.xml: note: compiling XML.
note: including /data/data/com.termux/files/home/github-upload-dealy/project//toolz/android.jar.
note: linking package 'com.helloworld' using package ID 7f.
note: merging archive build/resources.zip.
note: merging 'layout/activity_main' from compiled file res/layout/activity_main.xml.
note: enabling pre-O feature split ID rewriting.
note: collapsing resource versions for minimum SDK 17.
AndroidManifest.xml: note: writing to archive (keep_raw_values=false).
note: writing AndroidManifest.xml to archive.
note: linking res/layout/activity_main.xml (com.helloworld:layout/activity_main).
res/layout/activity_main.xml: note: writing to archive (keep_raw_values=false).
note: writing res/layout/activity_main.xml to archive.
note: writing resources.arsc to archive.
---------------- Using javac 17-internal ---------------
[parsing started SimpleFileObject[/data/data/com.termux/files/home/github-upload-dealy/project/src/com/helloworld/MainActivity.java]]
[parsing completed 81ms]
[parsing started SimpleFileObject[/data/data/com.termux/files/home/github-upload-dealy/project/build/com/helloworld/R.java]]
[parsing completed 4ms]
[loading /9/java.security.sasl/module-info.sig]
[loading /9/jdk.jlink/module-info.sig]
[loading /9/java.base/module-info.sig]
[loading /9/jdk.zipfs/module-info.sig]
[loading /9/java.security.jgss/module-info.sig]
[loading /9/java.se.ee/module-info.sig]
[loading /9/jdk.xml.dom/module-info.sig]
[loading /9/jdk.dynalink/module-info.sig]
[loading /9/jdk.crypto.ec/module-info.sig]
[loading /9/java.xml.bind/module-info.sig]
[loading /9/jdk.rmic/module-info.sig]
[loading /9/java.xml/module-info.sig]
[loading /9/java.corba/module-info.sig]
[loading /9/java.rmi/module-info.sig]
[loading /9/jdk.management.agent/module-info.sig]
[loading /9/java.se/module-info.sig]
[loading /9/java.xml.ws/module-info.sig]
[loading /9/jdk.management/module-info.sig]
[loading /9/jdk.naming.rmi/module-info.sig]
[loading /9/jdk.naming.dns/module-info.sig]
[loading /9/java.management.rmi/module-info.sig]
[loading /9/java.transaction/module-info.sig]
[loading /9/jdk.security.auth/module-info.sig]
[loading /9/jdk.localedata/module-info.sig]
[loading /9/jdk.jsobject/module-info.sig]
[loading /9/jdk.accessibility/module-info.sig]
[loading /9/jdk.editpad/module-info.sig]
[loading /9/jdk.crypto.cryptoki/module-info.sig]
[loading /9/java.instrument/module-info.sig]
[loading /9/jdk.compiler/module-info.sig]
[loading /9/jdk.jshell/module-info.sig]
[loading /9/java.naming/module-info.sig]
[loading /9/java.management/module-info.sig]
[loading /9/jdk.sctp/module-info.sig]
[loading /9/jdk.hotspot.agent/module-info.sig]
[loading /9/jdk.jstatd/module-info.sig]
[loading /9/jdk.jcmd/module-info.sig]
[loading /9/jdk.javadoc/module-info.sig]
[loading /9/java.sql.rowset/module-info.sig]
[loading /9/jdk.jdi/module-info.sig]
[loading /9/java.scripting/module-info.sig]
[loading /9/jdk.incubator.httpclient/module-info.sig]
[loading /9/java.desktop/module-info.sig]
[loading /9/jdk.security.jgss/module-info.sig]
[loading /9/jdk.jdeps/module-info.sig]
[loading /9/jdk.scripting.nashorn/module-info.sig]
[loading /9/java.activation/module-info.sig]
[loading /9/java.xml.ws.annotation/module-info.sig]
[loading /9/jdk.policytool/module-info.sig]
[loading /9/jdk.jdwp.agent/module-info.sig]
[loading /9/java.sql/module-info.sig]
[loading /9/jdk.attach/module-info.sig]
[loading /9/java.compiler/module-info.sig]
[loading /9/java.smartcardio/module-info.sig]
[loading /9/java.prefs/module-info.sig]
[loading /9/java.datatransfer/module-info.sig]
[loading /9/jdk.net/module-info.sig]
[loading /9/jdk.unsupported/module-info.sig]
[loading /9/jdk.pack/module-info.sig]
[loading /9/java.logging/module-info.sig]
[loading /9/jdk.charsets/module-info.sig]
[loading /9/jdk.httpserver/module-info.sig]
[loading /9/java.xml.crypto/module-info.sig]
[loading /9/jdk.jconsole/module-info.sig]
[loading /9/jdk.jartool/module-info.sig]
[search path for source files: /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar]
[search path for class files: /data/data/com.termux/files/usr/opt/openjdk/lib/modules,/data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/app/Activity.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/LayoutInflater.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/LayoutInflater$Factory2.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/LayoutInflater$Factory.class)]
[loading /9A/java.base/java/lang/Object.sig]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/Window.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/Window$Callback.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/KeyEvent.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/KeyEvent$Callback.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/os/Parcelable.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/InputEvent.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/View.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/View$OnCreateContextMenuListener.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/graphics/drawable/Drawable.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/graphics/drawable/Drawable$Callback.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/accessibility/AccessibilityEventSource.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/ComponentCallbacks2.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/ComponentCallbacks.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ContextThemeWrapper.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/ContextWrapper.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/Context.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/os/Bundle.class)]
[loading /9A/java.base/java/lang/Deprecated.sig]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewDebug.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewDebug$ExportedProperty.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewDebug$IntToString.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewDebug$FlagToString.class)]
[loading /879A/java.base/java/lang/Override.sig]
[loading /879A/java.base/java/lang/annotation/Annotation.sig]
[loading /879A/java.base/java/lang/annotation/Retention.sig]
[loading /879A/java.base/java/lang/annotation/RetentionPolicy.sig]
[loading /879A/java.base/java/lang/annotation/Target.sig]
[loading /9A/java.base/java/lang/annotation/ElementType.sig]
[checking com.helloworld.MainActivity]
[loading /879A/java.base/java/io/Serializable.sig]
[loading /9/java.base/java/util/List.sig]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/pm/PackageManager.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/pm/PackageManager$NameNotFoundException.class)]
[loading /879A/java.base/java/lang/Error.sig]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/util/AndroidException.class)]
[loading /879A/java.base/java/lang/Exception.sig]
[loading /879ABCDEFG/java.base/java/lang/Throwable.sig]
[loading /879A/java.base/java/lang/RuntimeException.sig]
[loading /9A/java.base/java/lang/Class.sig]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/IntentSender.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/content/IntentSender$SendIntentException.class)]
[loading /879A/java.base/java/io/IOException.sig]
[loading /879A/java.base/java/io/FileNotFoundException.sig]
[loading /879A/java.base/java/lang/AutoCloseable.sig]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/webkit/WebView.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/widget/AbsoluteLayout.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewGroup.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/webkit/WebSettings.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewTreeObserver.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewTreeObserver$OnGlobalFocusChangeListener.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewGroup$OnHierarchyChangeListener.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewParent.class)]
[loading /data/data/com.termux/files/home/github-upload-dealy/project/toolz/android.jar(/android/view/ViewManager.class)]
[loading /9A/java.base/java/lang/String.sig]
[wrote build/classes/com/helloworld/MainActivity.class]
[checking com.helloworld.R]
[wrote build/classes/com/helloworld/R$id.class]
[wrote build/classes/com/helloworld/R$layout.class]
[wrote build/classes/com/helloworld/R$string.class]
[wrote build/classes/com/helloworld/R.class]
[total 2448ms]
---------------d8:
processing com/helloworld/MainActivity.class...
processing com/helloworld/R$id.class...
processing com/helloworld/R$layout.class...
processing com/helloworld/R$string.class...
processing com/helloworld/R.class...
---------------zip:
        zip warning: needs unzip 0.0 on system type 0: AndroidManifest.xml
        zip warning: needs unzip 0.0 on system type 0: res/layout/activity_main.xml
        zip warning: needs unzip 0.0 on system type 0: resources.arsc
  adding: classes.dex   (in=2108) (out=1076) (deflated 49%)
total bytes=5992, compressed=3161 -> 47% savings
---------------zipalign:
Verifying alignment of ../zipout.apk (4)...
      49 AndroidManifest.xml (OK - compressed)
     888 res/layout/activity_main.xml (OK - compressed)
    1264 resources.arsc (OK)
    2305 classes.dex (OK - compressed)
Verification succesful
---------------apksigner:
Signed


...if success, result is /data/data/com.termux/files/home/github-upload-dealy/project//build/final.apk
```
