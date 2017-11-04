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
```c#
// Fade to a custom opacity (20%)
gameObject.FadeTo(0.2f, 0.8f);
```

### Transitions
Crayon gives you really simple functions for tweening common properties like position, rotation, size, and color.
```c#
// Tween to red over 800ms
Color32 red = new Color32(255, 0, 0, 255);
gameObject.TransitionToColor(newColor, 0.8f);
```
```c#
// Tween to hex color -
// Crayon will automatically convert to RGBA
gameObject.TransitionToColor("#FF0000", 0.8f);
```
```c#
// Tween position, relative to current localPosition
gameObject.TransitionToRelativePosition(new Vector3(0.0f, 1.0f, 0.0f));
```
```c#
// Tween position, to an absolute position in world space
gameObject.TransitionToAbsolutePosition(new Vector3(9.0f, 9.0f, 9.0f));
```
```c#
// Tween to rotation, based on current rotation
gameObject.TransitionToPositionAbsolute(new Vector3(9.0f, 9.0f, 9.0f));
```

### States
```c#
// Your interaction method
private void OnFocus() {
  // Crayon's state switcher
  gameObject.SetState(hover);
}
```
