# Crayon

Crayon is a lightweight, 3D UI toolkit for Unity. It was made for 3D UI designers who prefer working with GameObjects and TextMeshes over the 2D-oriented Unity GUI Canvas system.

Crayon makes it easier to set states and transitions for the following properties:
+ Opacity
+ Color
+ Position
+ Rotation
+ Scale

## Usage

Crayon contains several extension methods for the GameObject class, so you don't need to constantly call the Crayon namespace.

### Fade In/Out
It doesn't matter if your gameObject is text, sprite, or mesh...
Crayon will figure that out for you. Fades and transitions are applied to all children automatically.
```c#
// Fade In
gameObject.FadeIn(0.8f);
```
```c#
// Fade with easing
gameObject.FadeIn(0.8f, Easing.Linear);
```
```c#
// Instantiate a new GameObject and fade it in
gameObject.FadeInNew(0.8f);
```
```c#
// Fade Out
gameObject.FadeOut(0.8f);
```
```c#
// Fade Out and Destroy
gameObject.FadeOut(0.8f, true);
```
```c#
// Fade to a custom Opacity
gameObject.FadeTo();
```

### States
```c#
// Your interaction method
private void OnFocus() {
  // Crayon's state switcher
  gameObject.SetState(hover);
}
```
