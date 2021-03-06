---
author: scottmill
ms.assetid: a2751e22-6842-073a-daec-425fb981bafe
title: Visual Layer
description: The Windows.UI.Composition API gives you access to the composition layer between the framework layer (XAML), and the graphics layer (DirectX).
ms.author: scotmi
ms.date: 02/08/2017
ms.topic: article
ms.prod: windows
ms.technology: uwp
keywords: windows 10, uwp
---
# Visual Layer

\[ Updated for UWP apps on Windows 10. For Windows 8.x articles, see the [archive](http://go.microsoft.com/fwlink/p/?linkid=619132) \]

The Visual layer provides a high performance, retained-mode API for graphics, effects and animations and is the foundation for all UI across Windows devices.  You define your UI in a declarative manner and the Visual layer relies on graphics hardware acceleration to ensure your content, effects and animations are rendered in a smooth, glitch-free manner independent of the app's UI thread.   
  
## Notable highlights: 
* Familiar WinRT APIs 
* Architected for more dynamic UI and interactions 
* Concepts aligned with design tools 
* Linear scalability with no sudden performance cliffs 
  
Your Windows UWP apps are already using the Visual layer via one of the UI frameworks. You can also take advantage of Visual layer directly for custom rendering, effects and animations with very little effort. 

![UI framework layering: the framework layer (Windows.UI.XAML) is built on the visual layer (Windows.UI.Composition) which is build on the graphics layer (DirectX)](images/layers-win-ui-composition.png)


## What's in the Visual layer? 
The primary functions of the Visual layer are: 
1. Content: Lightweight compositing of custom drawn content 
2. Effects: Realtime UI effects system whose effects can be animated, chained and customized 
3. Animations: Expressive, framework-agnostic animations running independent of the UI thread 
  
### Content 
Content is hosted, transformed and made available for use by the animation and effects system using visuals. Everything in the [**Visual**](https://msdn.microsoft.com/library/windows/apps/Dn706858) class inherits from inherits from the base Visual including a  [**ContainerVisual**](https://msdn.microsoft.com/library/windows/apps/Dn706810) to allow for children to create trees of visuals and a [**SpriteVisual**](https://msdn.microsoft.com/library/windows/apps/Mt589433) that contain content and can be painted by CompositionBrushs.  

For more information, see the [Composition Visual](composition-visual-tree.md) overview.
 
### Effects 
The Effects system inside Windows.UI.Composition lets you apply a chain of filter and transparency effects to a Visual or a tree of Visuals. Effects work in conjunction with the Animation system, allowing users to achieve smooth and dynamic animations of Effect properties, rendered independent of the UI thread. Effects in the Visual Layer provide the creative building blocks that can be combined and animated to construct tailored and interactive experiences.  
In addition to animatable effect chains, the Visual Layer also supports a Lighting model that allows Visuals to mimic material properties by responding to animatable Lights. Visuals may also cast Shadows. Lighting and Shadows can be combined to create a perception of depth and realism. 

For more information, see the [Composition Effects](composition-effects.md) overview.
  
### Animations 
The animation system inside Windows.UI.Composition lets you move visuals, animate effects, and drive transformations, clips, and other properties.  It is a framework agnostic system that has been designed from the ground up with performance in mind.  It runs independently from the UI thread to ensure smoothness and scalability.  While it lets you use familiar KeyFrame animations to drive property changes over time, it also lets you set up mathematical relationships between different properties, including user input, letting you directly craft seamless choreographed experiences. 

For more information, see the [Composition animations](composition-animation.md) overview.

### Working with your XAML UWP app
In addition to creating a visual tree from scratch, the Composition API can interoperate with an existing XAML UI using the [**ElementCompositionPreview**](https://msdn.microsoft.com/library/windows/apps/Mt608976) class in [**Windows.UI.Xaml.Hosting**](https://msdn.microsoft.com/library/windows/apps/Hh701908).

For more information, see the [Using XAML](using-the-visual-layer-with-xaml.md) overview.


## Additional resources 
* [**Full reference documentation for the API**](https://msdn.microsoft.com/library/windows/apps/Dn706878)
* Advanced UI and Composition samples in the [WindowsUIDevLabs GitHub](https://github.com/microsoft/windowsuidevlabs)
* [Windows.UI.Composition Sample Gallery](https://aka.ms/winuiapp)  
* [@windowsui Twitter feed ](https://twitter.com/windowsui)
* Read Kenny Kerr's MSDN Article on this API: [Graphics and Animation - Windows Composition Turns 10](https://msdn.microsoft.com/magazine/mt590968)
