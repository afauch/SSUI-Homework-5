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
Unity can make opacity a pain, but Crayon makes it easy. It doesn't matter if your gameObject is text, sprite, or mesh...
Crayon will figure that out for you. Fades are applied to all children automatically.
```c#
// Fade in over 800ms
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

### Transitions
Crayon gives you really simple functions for tweening common properties like color, position, rotation, size, and opacity.
```c#
// Tween to red over 800ms
Color32 red = new Color32(255, 0, 0, 255);
gameObject.TransitionColor(newColor, 0.8f);
```
```c#
// Tween to hex color -
// Crayon will automatically convert to RGBA
gameObject.TransitionColor("#FF0000", 0.8f);
```
```c#
// Tween position, relative to current localPosition
gameObject.TransitionRelativePosition(new Vector3(0.0f, 1.0f, 0.0f), 0.8f);
```
```c#
// Tween position, to an absolute position in world space
gameObject.TransitionAbsolutePosition(new Vector3(9.0f, 9.0f, 9.0f), 0.8f);
```
```c#
// Tween to rotation
gameObject.TransitionRotation(new Vector3(9.0f, 9.0f, 9.0f), 0.8f, Easing.Cubic);
```
```c#
// Tween to opacity
gameObject.TransitionOpacity(0.2f, 0.8f);
```

### States
```c#
// Your interaction method
private void OnFocus() {
  // Crayon's state switcher
  gameObject.SetState(hover);
}
```
