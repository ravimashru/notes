# Initializing `@Binding` variables

You can't initialize `@Binding` variables!

   

A binding is not a source of truth.

The source of truth should be something like `@State`.

Binding is just passed to child views with read/write access from source of truth

Source: [https://developer.apple.com/forums/thread/120394](https://developer.apple.com/forums/thread/120394)