# notepad-.dll
plug ins for notepad++

Alright, let's dive into Notepad++ plugin development!

It looks like you have a few options for creating Notepad++ plugins, with the most common languages being C++ and C#. There are also scripting plugins like PythonScript or LuaScript if you prefer a less compiled approach.

Here's a breakdown of the documentation and resources available:

**1. Official Notepad++ User Manual - Plugins Section:**

* **Plugin Communication:** This is crucial for understanding how your plugin will interact with Notepad++. It explains the use of messages and notifications (like `SendMessage` calls) to get information from Notepad++ or instruct it to perform tasks. This is where you'll find details on `NPPM_` messages and `Scintilla` messages (for interacting with the editor component itself).
    * [https://npp-user-manual.org/docs/plugin-communication/](https://npp-user-manual.org/docs/plugin-communication/)
* **How to Develop a Plugin:** This section provides an overview of the development process and links to the plugin template.
    * [https://npp-user-manual.org/docs/plugins/#how-to-develop-a-plugin](https://npp-user-manual.org/docs/plugins/)
* **Plugins Admin:** Information on how plugins are listed, installed, removed, and updated within Notepad++. This is important if you plan to share your plugin.
    * [https://npp-user-manual.org/docs/plugins/#plugins-admin](https://npp-user-manual.org/docs/plugins/)

**2. Plugin Templates & Boilerplates:**

* **C# .NET Notepad++ Plugin Template:** This is a popular option for C# developers. It provides a Visual Studio template that sets up the basic structure for your plugin, including pre-added methods and menu commands.
    * Direct download: [http://sourceforge.net/projects/sourcecookifier/files/other%20plugins/NppPlugin.NET.v0.5.zip/download](http://sourceforge.net/projects/sourcecookifier/files/other%20plugins/NppPlugin.NET.v0.5.zip/download)
    * GitHub repository with more active maintenance: [https://github.com/kbilsted/NotepadPlusPlusPluginPack.Net](https://github.com/kbilsted/NotepadPlusPlusPluginPack.Net) (This one is a spin-off of Don Ho's original demo.)
* **C++ Notepad++ Plugin Template (GitHub):** A skeleton for creating plugins with MinGW (GCC for Windows).
    * [https://github.com/diegocr/mingw-nppskeleton](https://github.com/diegocr/mingw-nppskeleton)
    * There's also a general `plugindemo` on the official Notepad++ GitHub, but some users recommend creating your own structure as the template might be a bit dated for modern C++.
    * [https://github.com/npp-plugins/plugindemo](https://github.com/npp-plugins/plugindemo)

**3. Community and Tutorials:**

* **Notepad++ Community Forum - Plugin Development Category:** This is an excellent place to ask questions, get support, and see what other developers are working on.
    * [https://community.notepad-plus-plus.org/category/5/notepad-plugin-development](https://community.notepad-plus-plus.org/category/5/notepad-plugin-development)
* **FervorT - "How to Develop a Notepad++ Plugin" (C# .NET):** A step-by-step tutorial for building a simple plugin using C# .NET.
    * [https://fervort.com/blog/2016/01/how-to-develop-a-notepad-plugin/](https://fervort.com/blog/2016/01/how-to-develop-a-notepad-plugin/)
* **VBForums - "Create A Basic Notepad++ Plugin Using Notepad++ 64Bit, Visual Studio And C#":** Another C# focused tutorial.
    * [https://www.vbforums.com/showthread.php?896113-Create-A-Basic-Notepad-Plugin-Using-Notepad-64Bit-Visual-Studio-And-C](https://www.vbforums.com/showthread.php?896113-Create-A-Basic-Notepad-Plugin-Using-Notepad-64Bit-Visual-Studio-And-C)
* **PythonScript Plugin Documentation:** If you're interested in scripting, the PythonScript plugin provides its own API for interacting with Notepad++. This can be a quicker way to develop simpler functionalities without full compilation.
    * [https://npppythonscript.sourceforge.net/docs/latest/notepad.html](https://npppythonscript.sourceforge.net/docs/latest/notepad.html)

**Key Concepts to Understand:**

* **`DllMain` and Plugin Interface Functions:** When developing in C++ or C#, you'll need to implement specific functions that Notepad++ calls to initialize and communicate with your plugin (e.g., `setInfo`, `getName`, `getFuncsArray`, `beNotified`).
* **Notepad++ Messages (`NPPM_`):** These are messages you send to Notepad++ to control its behavior (e.g., opening files, getting current buffer ID, running menu commands).
* **Scintilla Messages:** Notepad++ uses the Scintilla editing component. To manipulate text within the editor, get cursor position, etc., you'll use Scintilla messages. The Scintilla documentation is a separate but essential resource.
* **Dialog Boxes/UI:** If your plugin requires user input beyond simple menu commands, you'll need to create dialog boxes. For C# this can be done easily with Windows Forms. For C++ this involves using the Win32 API for dialogs, which can be more complex.
* **Debugging:** Instructions on how to debug your plugin within Visual Studio are often included in the templates or tutorials.

**Getting Started:**

1.  **Choose your language:** C# with Visual Studio and the .NET template is often recommended for beginners due to its ease of use for UI elements. If you're comfortable with C++, you can use that.
2.  **Download a template:** Start with one of the recommended plugin templates for your chosen language.
3.  **Follow a tutorial:** The tutorials provide step-by-step guidance on setting up your development environment and creating a basic "Hello World" plugin.
4.  **Explore the API:** Once you have a basic plugin working, dive into the Notepad++ User Manual's "Plugin Communication" section and the Scintilla documentation to understand the full range of functionalities you can implement.

Good luck with your Notepad++ plugin development!
