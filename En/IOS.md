🔗 Relevant Links 🔗

►Xcode - download latest version

https://developer.apple.com/xcode/

►Apple USB-C to Lightning Cable (I bought the 2m one)

https://www.apple.com/shop/product/MM0A3AM/A/usb-c-to-lightning-cable-1-m

►Visual Studio Code

https://code.visualstudio.com/

►Visual Studio Code and Unity Instructions

https://code.visualstudio.com/docs/other/unity

►.NET Core SDK

https://dotnet.microsoft.com/download

►Mono Stable Channel

https://www.mono-project.com/download/stable/#download-mac

►Extensions

➡C# (Required)

https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp

➡Debugger for Unity (Optional -- Recommended)

https://marketplace.visualstudio.com/items?itemName=Unity.unity-debug

➡Unity Tools (Optional -- Recommended)

https://marketplace.visualstudio.com/items?itemName=Tobiah.unity-tools

➡Unity Code Snippets (Optional)

https://marketplace.visualstudio.com/items?itemName=kleber-swf.unity-code-snippets

➡C# XML Documentation (Optional)

https://marketplace.visualstudio.com/items?itemName=k--kato.docomment

➡Halcyon Theme (Optional)

https://marketplace.visualstudio.com/items?itemName=brittanychiang.halcyon-vscode

Setting up Unity Development on Mac:

1. Install Visual Studio Code for Mac and go through the installation process

2. Close out of Unity and Visual Studio Code

3. Install Mono Stable Channel for and .NET SDK for Visual Studio Code

4. I recommend restarting after installing these

5. Open Unity, install the VS Code package if not installed, set External Tools to Visual Studio Code, Click Regenerate Project Files

6. Edit -- Open C# Assets (if you ever have a problem with VS Code not recognizing your code, close out of VS Code and Open it with this button)

7. Download C#, Unity Tools, Unity Debugger, Unity Code Snippets, Unity Snippets, C# XML Documentation, using Halcyon Theme

8. Settings: -Omnisharp: Use Modern Net Turn Off. Set Omnisharp Mono Path (/Library/Frameworks/Mono.framework/Versions/Current”, Disable Telemetry (collect analytics on you), Turn off CodeLens, inlay hints parameters c#,

9. Close VS Code, word wrap to word wrap column (search wrap), wrapping indent (indent)

10. Edit -- Open C# Assets

11. Make sure Intellisense is working, fire in bottom right, opens up terminal and tells you if there are any errors, choose correct solution

12. Go to Debug Tab, Create Launch.json Unity Debugger, Place Breakpoint, Press Play, Go to Unity and Enable Debugging Session, Press Play in Unity, then you can step through the code and see details

Things to do if Intellisense is not working:

*Uninstall and Reinstall VS Code, Mono, and .NET Packages

*Assets/Open C# Project

*Edit/Preferences/External Tools/Regenerate CSPROJ files

*Check Omnisharp Logs

Summary of the steps to Build for Testing on IOS:

1. Download Xcode from Apple's Developer Website (link above)

2. Add iOS Module support in Unity Hub to the version you are using

3. In Build Settings Switch to the new iOS platform

4. Select Development Build

5. Make sure API version is minimum 12.0 for iOS in the Player Settings

6. Build & Run - if error that cannot find Xcode path, go to Xcode settings, then Location, then reset the Set Command Line option to Xcode (you will need to enter your Apple ID password) (just reclick it, I don't know why it fixes it)

7. Xcode will now pop up with the build. You need to Enable Automatic Signing under the Signing and Capabilities Tab, and create a new Team with yourself if you haven't already.

8. Connect your phone to the computer and enable Developer Mode on the Phone (Settings - Privacy & Security - Developer Mode - Check Yes and Restart Phone)

9. In Xcode, at the top bar make sure your phone is selected as the output device.

10. Click play on the top left to build to phone.

11. Trust the app on your phone, go to General - VPN & Device Management - Click Your Developer App - and Click Trust

12. Tada! Click your app and allow permissions as necessary.