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
```c#
// Fade in a GameObject
// It doesn't matter if it's text, sprite, or mesh
gameObject.FadeIn(0.8, Easing.Linear);
```
```c#
// Fade in a GameObject
gameObject.FadeIn(0.8);
```
```c#
// Instantiate a new GameObject and fade it in
gameObject.FadeInNew(0.8);
```
```c#
// Fade Out
gameObject.FadeOut(0.8);
```
```c#
// Fade Out and Destroy
gameObject.FadeOut(0.8, true);
```

### States
```c#
// Your interaction method
private void OnFocus() {
  // Crayon's state switcher
  gameObject.SetState(hover);
}
```
