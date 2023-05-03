# Default ScriptHookVDotNet Template

This is a basic template for creating a ScriptHookVDotNet v3 script for Grand Theft Auto V. The template provides a structure for handling different game events such as Tick, Aborted, KeyDown, and KeyUp.

## Features

- Basic structure for a ScriptHookVDotNet v3 script
- Event handling for Tick, Aborted, KeyDown, and KeyUp events
- Example code snippets for various event handlers

## Installation
- Open Visual Studio
- Create a new project
- Select "Class Library (.NET Framework)"
- Enter a Project name, select .NET Framework 4.8 (or latest version), edit any other fields needed and create your new project
- Copy and paste either the template that includes the comments (very useful comments!) or the template below in this Readme that includes no comments
- To build your solution, use Ctrl + Shift + B, navigate to your solution directory > bin > Debug > <Name Of Your Script>.dll, move that to your GTA:V "Scripts" directory
- It's higly suggested to create a post-build event in Visual Studio to automatically copy your compiled mod DLL to your scripts folder. Follow this simple guide here: [Visual Studio Automatic DLL Copy](Visual Studio Automatic DLL Copy)
- For more infomration, please follow the official ScriptHookVDotNet Wiki page: [ScriptHookVDotNet v3](https://github.com/crosire/scripthookvdotnet/releases)
- I've also created a YouTube video series on creating ScriptHookVDotNet scripts here: [GTA:V ScriptHookV Coding: Part One | Settings Up Dev Environment](https://youtu.be/OZ_SUy0AXL4)

## Have Suggestions?
Suggestions are always welcome! Please use the Issue tracker to leave your suggestions.

## Credits
- VideoWarfare (me)

## Template Code

```csharp
using System;
using System.Drawing;
using System.Windows.Forms; // Add this line to import the Keys namespace
using GTA;
using GTA.Math;

// Replace "YourNamespace" with the namespace you want to use for your project
namespace Default_ScriptHook_Template
{
    // Replace "YourScript" with a descriptive name for your script class
    public class Default_ScriptHook_Template : Script
    {
        // Constructor
        public Default_ScriptHook_Template()
        {
            // Subscribe to Tick event (called on every frame)
            Tick += OnTick;

            // Subscribe to Aborted event (called when the script is being stopped or unloaded)
            Aborted += OnAbort;

            // Subscribe to KeyDown event (called when a key is initially pressed)
            KeyDown += OnKeyDown;

            // Subscribe to KeyUp event (called when a key is released)
            KeyUp += OnKeyUp;

            // Add any additional setup code here
        }

        // The Tick event handler
        private void OnTick(object sender, EventArgs e)
        {
            // Add your code here to be executed on every frame

            // Example: Check if the player is in a police vehicle
            // if (Game.Player.Character.IsInPoliceVehicle)
            // {
            //     // Your code here
            // }
        }

        // The Abort event handler
        private void OnAbort(object sender, EventArgs e)
        {
            // Add any cleanup code here, such as unsubscribing from events, stopping timers, or disposing resources

            // Example: Unsubscribe from Tick, Aborted, KeyDown, and KeyUp events
            // Tick -= OnTick;
            // Aborted -= OnAbort;
            // KeyDown -= OnKeyDown;
            // KeyUp -= OnKeyUp;
        }

        // The KeyDown event handler
        private void OnKeyDown(object sender, KeyEventArgs e)
        {
            // Add your code here to be executed when a key is initially pressed

            // Example: Check if the J key is pressed
            // if (e.KeyCode == Keys.J)
            // {
            //     // Your code here
            // }
        }

        // The KeyUp event handler
        private void OnKeyUp(object sender, KeyEventArgs e)
        {
            // Add your code here to be executed when a key is released

            // Example: Check if the K key is released
            // if (e.KeyCode == Keys.K)
            // {
            //     // Your code here
            // }
        }
    }
}
