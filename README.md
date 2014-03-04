***** UPDATE *****

(March 4th, 2014)

People have been having difficulty getting this working. There is a thread on Google Groups: https://groups.google.com/forum/#!topic/echoprint/Zi_ip49Xgds.

I *believe* the issue is related to the fact that the prior project was built for an older XCode + Compiler (GCC). In order to "upgrade" the project I had to bump up to LLVM which is now the default and this results in some issues with the C++ portions of the project. I am currently out of time to work on this, if you have a solution I welcome your pull requests. 


OVERVIEW

This is an upgraded version of the Echoprint Sample iOS Project.

- Works in XCode 5.0 + iOS 7
- Modernized Objective-C
- Modernized UIKit and other legacy project files
- Updated ASIHTTP to more current version
- Added Cocoapods
- Builds in the echoprint-codegen-ios library as a sub-project
- Added project dependency on lbstdc++.6.0.9.dylib that didn't seem to be required before

INSTALL / SETUP INSTRUCTIONS

- The project requires a depdendency on libechoprint-codegen-ios.a and thus needs to build the sub-project (see below)
- Run pod install to setup the pod files in the project root
- Download Boost 1.5+ and unzip it someplace useful like /Users/YOUR_USER_GOES_HERE_REPLACE_THIS/Development/boost
- Open the project workspace created by Cocoapods (not the main project)
- In "echoprint-codegen-ios.xcconfig" in the "echoprint-codegen-ios" sub-project, make sure this line points to your boost directory:

HEADER_SEARCH_PATHS = /Users/YOUR_USER_GOES_HERE_REPLACE_THIS/Development/boost

It should build for you. 


