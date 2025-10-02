# RA-Cheevos-Bridge
A Fix for the RetroArch Achievements Login Error

Official Release post: https://www.patreon.com/posts/139800541

If you use RetroAchievements with RetroArch, you've probably seen the annoying "Login failed" error message that pops up when your session expires. This forces you to go back into the settings and re-enter your password, which is especially frustrating when using a frontend.

To solve this once and for all, I've created a "set and forget" helper app called RA Cheevos Bridge.

The Problem

For security, after you log into RetroAchievements, RetroArch saves a temporary session token and deletes your password from the config file. When that token expires days later, RetroArch has no password to get a new one, and the login fails.

The Solution

RA Cheevos Bridge is a lightweight, invisible app that acts as a middleman. You point your frontend to “RA_Bridge.exe” instead of retroarch.exe and you’re done. Every time you launch a game this app forces RetroArch to perform a fresh login every single time, generating a new token and completely preventing the error from ever appearing.

Key Features

Set and Forget: Two minutes setup.

Completely Invisible:  You won't see any extra windows or pop-ups.

Frontend Friendly: It passes all commands through, so it works perfectly with frontends like LaunchBox, Playnite, EmulationStation, etc.

Failsafe: If the bridge app is ever forcefully closed, it will automatically close RetroArch too, preventing orphaned processes.

How to Use:

Step 1: Download the file (unblock the downloaded zip) and extract it.

Step 2: Copy the extracted files “RA_Bridge.exe”, “cheevos_login.ini” and “_internal folder” into your portable RetroArch directory, right next to retroarch.exe.

Step 3: Open “cheevos_login.ini” with any text editor and replace the placeholder details with your own username and password. Save and close the file.

Step 4: Configure Your Setup
You have three options depending on your case:

Method A (For Most Frontends):

In your frontend's emulator settings (launchbox for example), simply change the executable path from ...\retroarch.exe to ...\RA_Bridge.exe.

Method B (For Frontends with "retroarch.exe" hardcoded):

Rename your original retroarch.exe to retroarch_real.exe and rename RA_Bridge.exe to retroarch.exe.

Method C (Standalone Retroarch)

If you use RetroArch without a frontend, just run "RA_Bridge.exe".]

That's it! The next time you launch a game, the login will be handled automatically.

A Quick Note on Security:The data stored in “cheevos_login.ini” is only used locally, to force RetroArch login every time instead of using the temporary token.
