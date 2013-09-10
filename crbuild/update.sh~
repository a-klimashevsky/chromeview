# Updates this project with the Chrome build files.
# This script assumes the Chrome build VM is up at ubuntu

# Clean up.
rm -r assets/*
rm -r libs/*
rm -r src/com/googlecode
rm -r src/org/chromium

# ContentShell core -- use this if android_webview doesn't work out.
#scp alex@ubuntu:chromium/src/out/Release/content_shell/assets/* \
#    assets/
#scp -r alex@ubuntu:chromium/src/out/Release/content_shell_apk/libs/* \
#    libs
#scp -r alex@ubuntu:chromium/src/content/shell/android/java/res/* res
#scp -r alex@ubuntu:chromium/src/content/shell/android/java/src/* src
#scp -r alex@ubuntu:chromium/src/content/shell_apk/android/java/res/* res

# android_webview
scp alex@ubuntu:chromium/src/out/Release/android_webview_apk/assets/*.pak \
    assets
scp -r alex@ubuntu:chromium/src/out/Release/android_webview_apk/libs/* \
    libs
rm libs/**/gdbserver
scp -r alex@ubuntu:chromium/src/android_webview/java/src/* src/

## Dependencies inferred from android_webview/Android.mk

# Resources.
scp -r alex@ubuntu:chromium/src/content/public/android/java/resource_map/* src/
scp -r alex@ubuntu:chromium/src/ui/android/java/resource_map/* src/

# ContentView dependencies.
scp -r alex@ubuntu:chromium/src/base/android/java/src/* src/
scp -r alex@ubuntu:chromium/src/content/public/android/java/src/* src/
scp -r alex@ubuntu:chromium/src/media/base/android/java/src/* src/
scp -r alex@ubuntu:chromium/src/net/android/java/src/* src/
scp -r alex@ubuntu:chromium/src/ui/android/java/src/* src/
scp -r alex@ubuntu:chromium/src/third_party/eyesfree/src/android/java/src/* src/

# Strip a ContentView file that's not supposed to be here.
rm src/org/chromium/content/common/common.aidl

# Get rid of the .svn directory in eyesfree.
rm -r src/com/googlecode/eyesfree/braille/.svn

# Browser components.
scp -r alex@ubuntu:chromium/src/components/web_contents_delegate_android/android/java/src/* src/
scp -r alex@ubuntu:chromium/src/components/navigation_interception/android/java/src/* src/

# Generated files.
scp -r alex@ubuntu:chromium/src/out/Release/gen/templates/* src/

# JARs.
scp -r alex@ubuntu:chromium/src/out/Release/lib.java/guava_javalib.jar libs/
scp -r alex@ubuntu:chromium/src/out/Release/lib.java/jsr_305_javalib.jar libs/

# android_webview generated sources. Must come after all the other sources.
scp -r alex@ubuntu:chromium/src/android_webview/java/generated_src/* src/
