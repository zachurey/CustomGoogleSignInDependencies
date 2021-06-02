# CustomGoogleSignInDependencies

**A custom GoogleSignInDependencies framework that replaces `GoogleSignInDependencies.frameworks` when the Firebase SDK is part of the Xcode Project.**

This is based off of this question on [stackoverflow](https://stackoverflow.com/questions/41217839/duplicate-symbols-when-integrating-firebase-and-google-sign-in-sdks-manually-wit).

This is custom framework was made for GoogleSignIn 5.0.2 and Firebase 7.11.1.

### How to use

1. Download the CustomGoogleSignInDependencies.framework file
2. Add the CustomGoogleSignInDependencies.framework to your Xcode Project
3. Under Targets -> Build Phases -> Link Binary with Libraries: Add the CustomGoogleSignInDependencies.framework file
5. Under Targets -> Build Phases -> Embeded Frameworks: Enable the checkmark next to "Copy only when installing". Also make sure you see CustomGoogleSignInDependencies.framework is in the list below this checkmark. (In order to see `Embeded Frameworks` you may have to first add GoogleSignIn, then under Target -> General -> Frameworks, Libraries, and Embedded Content check "Sign and Embed" next to the GoogleSignIn framework.)
6. Under Targets -> Build Settings -> Build Options: Make sure `Validate Workspace` is checked to yes.

**Make sure you still follow the instructions for the [GoogleSignIn SDK implementation](https://developers.google.com/identity/sign-in/ios/sdk).**

Errors this Framework fixes:
`35 duplicate symbols for architecture arm64`
```
duplicate symbol '_kGTMSessionFetcherElapsedIntervalWithRetriesKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherCompletionErrorKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherStatusDataContentTypeKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherNumberOfRetriesDoneKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherStatusDataKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherCompletionDataKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_GTMSessionFetcherAssertValidSelector' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_GTMFetcherApplicationIdentifier' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_OBJC_CLASS_$_GTMSessionFetcher' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_OBJC_METACLASS_$_GTMSessionFetcher' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherRetryDelayStartedNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherStartedNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherRetryDelayStoppedNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherStoppedNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherCompletionInvokedNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherStatusDomain' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherErrorDomain' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_GTMDataFromInputStream' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_GTMFetcherStandardUserAgentString' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_GTMFetcherCleanedUserAgentString' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_GTMFetcherSystemVersionString' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_OBJC_CLASS_$_GTMSessionCookieStorage' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_OBJC_METACLASS_$_GTMSessionCookieStorage' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherServiceSessionKey' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcherService_***************************.o)
duplicate symbol '_OBJC_CLASS_$_GTMSessionFetcherSessionDelegateDispatcher' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcherService_***************************.o)
duplicate symbol '_OBJC_METACLASS_$_GTMSessionFetcherSessionDelegateDispatcher' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcherService_***************************.o)
duplicate symbol '_kGTMSessionFetcherServiceSessionBecameInvalidNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcherService_***************************.o)
duplicate symbol '_OBJC_CLASS_$_GTMSessionFetcherService' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcherService_***************************.o)
duplicate symbol '_OBJC_METACLASS_$_GTMSessionFetcherService' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionFetcherService_***************************.o)
duplicate symbol '_OBJC_CLASS_$_GTMSessionUploadFetcher' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionUploadFetcher_***************************.o)
duplicate symbol '_OBJC_METACLASS_$_GTMSessionUploadFetcher' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionUploadFetcher_***************************.o)
duplicate symbol '_kGTMSessionFetcherUploadLocationObtainedNotification' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionUploadFetcher_***************************.o)
duplicate symbol '_kGTMSessionUploadFetcherMaximumDemandBufferSize' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionUploadFetcher_***************************.o)
duplicate symbol '_kGTMSessionUploadFetcherStandardChunkSize' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionUploadFetcher_***************************.o)
duplicate symbol '_kGTMSessionUploadFetcherUnknownFileSize' in:
    /Users/user/Library/Developer/Xcode/DerivedData/project-name/Build/Products/Debug-iphoneos/GTMSessionFetcherCore.o
    /Users/user/path/google_signin_sdk_5_0_2/GoogleSignInDependencies.framework/GoogleSignInDependencies(GTMSessionUploadFetcher_***************************.o)
ld: 35 duplicate symbols for architecture arm64
clang: error: linker command failed with exit code 1 (use -v to see invocation)
```
