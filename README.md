# React Native Dimensions Bug: Inconsistent Android Behavior After Rotation

This repository demonstrates a bug in React Native's `Dimensions.get('window')` API on Android. After screen rotation, the API sometimes returns incorrect window dimensions, leading to layout inconsistencies.

## Problem

The `Dimensions.get('window')` method is used to get the dimensions of the application window.  However, on some Android devices, after rotating the screen, the reported width and height values are smaller than the actual screen dimensions. This issue is intermittent and can be hard to reproduce reliably.

## Solution

The solution involves using the `Dimensions` API in conjunction with the `LayoutAnimation` API and handling the `onLayout` event. By waiting for the layout to complete after the rotation event, we can obtain accurate dimensions.