# AvaloniaApps

True Opensource Crossplatform Ui via modern databound controls.
 - Android
 - Ios
 - Windows
 - WASM

AXML Visual RAD designer in Winform
  - Upgraded WPF XAML
  - MvvM 

Better than WiseJ 
  - WPF Databound controls, better than frontend loaded Winform UI for the Web
 
 Wisej’s controls have a double life: the server side component and the client side widget. The server side component manipulates the client side widget as a whole and manages the layout between the components. The client side widget manages its internal layout and child widgets entirely on the client side.

 So… The Desktop component on the server knows only about the desktop widget and certain metrics, like the non-client area, borders, theme padding, colors, etc. Doesn’t know anything about the internal layout of the desktop widget and its child widgets.

 For example a Taskbar, in this case the child widgets are “workspace” and “taskbar”.

 The “taskbar” child widget is positioned at the bottom because it has a layout property named “edge” set to “south”. The parent desktop widget uses the “Dock” layout engine.

 In code, if you set the Dock property of the status bar to None and add the code below on startup, the status bar will dock below the taskbar.
```
this.statusBar1.Eval(
@”this.addListener(‘appear’, function(){
   this.resetUserBounds();
   App.Desktop._addBefore(this, App.Desktop.getChildControl(‘taskbar’), {top:null, left: null, edge:’south’});
  });”
);

```
The code above executes on the client when the status bar “appears”, which means that the corresponding html element is created and made visible, it removes the location and size set by the server, it changes the layout parent and docks it under the taskbar child widget.
---
## ReactUI MvvM Sample

https://docs.avaloniaui.net/docs/tutorials/todo-list-app

---
## WASM

https://docs.avaloniaui.net/docs/tutorials/running-in-the-browser
```
  dotnet workload install wasm-experimental wasm-tools

  dotnet new avalonia.xplat
```

