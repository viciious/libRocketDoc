---
layout: page
title: Debugger plugin
parent: cpp_manual
---

Rocket ships with an open-sourced visual debugger plugin that you can use and modify to aid you in development. You can try it out in the Rocket Invaders from Mars sample application by pressing SHIFT-~.

### Tools

The tools included with the debugger are:

#### On-screen log

The debugger puts in its own system interface layer to intercept the logging messages going out of Rocket. The log beacon (a little exclamation mark) will become visible in the top-right corner of its context when a new log message has been sent. You can open the log by clicking on the beacon or opening the debugger and clicking on the 'Message Log' button.

#### Outline renderer

If you click on the 'Outlines' button on the menu, the debugger will render red outlines around the bordered area of every element in the target context.

#### Visual debugger

If you click on the 'Element Info' button the menu, the visual debugger will open. When this is open, mouse clicks on the target context will be intercepted; any element clicked on will become the debugger's active element. The debugger will show the following about the active element:

* The content area (in blue), padding (in purple), border (in grey) and margin (in yellow) of the element on the debugged context.
* The element's attributes.
* The element's properties, and where they were declared.
* The position and size of the element's primary box.
* The ancestors of the element.
* The children of the element. 

If the debugger picks up another click on the active element, the click will fall through to the element itself.

As these tools are all open source, we encourage you to add more features if you find the debugger doesn't give you the information you need.

### Initialisation

To start the debugger, call Rocket::Debugger::Initialise() with the context you want the debugger menu rendered into. You'll need to include Rocket/Debugger.h.

```cpp
// Initialises the debug plugin. The debugger will be loaded into the given context.
// @param[in] context The Rocket context to load the debugger into.
// @return True if the debugger was successfully initialised
bool Initialise(Rocket::Core::Context* context);
```

The debugger's context is not necessarily the context being debugged, only the context it renders its elements into. When the debugger is initialised, however, it automatically begins debugging its context.

### Debugging another context

To debug another context, call the Rocket::Debugger::SetContext() method.

```cpp
// Sets the context to be debugged.
// @param[in] context The context to be debugged.
// @return True if the debugger is initialised and the context was switched, false otherwise.
bool SetContext(Rocket::Core::Context* context);
```

The debugger will then be ready for debugging elements in the new context.

### Controlling visibility

The IsVisible() and SetVisible() functions can be used to control the visibility of the debugger's elements.

```cpp
// Sets the visibility of the debugger.
// @param[in] visibility True to show the debugger, false to hide it.
void SetVisible(bool visibility);

// Returns the visibility of the debugger.
// @return True if the debugger is visible, false if not.
bool IsVisible();
```

### Source

You can find the source for the debugger plugin in the src/Rocket/Debugger/ directory within your Rocket installation. Build files are located in src/Rocket/Debugger/build. 