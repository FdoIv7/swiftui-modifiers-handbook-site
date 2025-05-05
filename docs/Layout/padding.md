---
id: padding
title: padding(_:)
sidebar_label: Padding
---

### What it is:

Adds space **inside** a view, between its content and its boundary - like putitng invisible breathing room around the content.

Think of it as telling SwiftUI:

> "Give this view some room to breathe - inside its own frame"

### When to use:

- You want to avoid your content being flush against edges.
- You’re spacing things evenly in a stack (e.g. vertical/horizontal layout)
- You want consistent spacing without manually placing Spacers or offsets.
- You’re layering borders/backgrounds and want a nicer visual margin.

### Watch out for:

- **Modifier order matters: .padding()** before **.border()** expands the border, not the other way around.
- Using **.padding()** alone adds **default (16 pt) padding on all sides** - specify a value if you want custom spacing.
- If stacking views tightly, multiple paddings can unintentionally add up and overflow your layout.

### `.padding()` in action:

<div style={{marginLeft: '2rem', marginTop: '2rem', width: '80%'}}>
  <img src={require('@site/static/img/layout/padding/padding_animation.gif').default} alt="Padding animation example" style={{ width: '100%', borderRadius: '8px' }} />
</div>

### How it looks in Xcode:

<div style={{marginLeft: '2rem', marginTop: '2rem', width: '80%'}}>
  <img src={require('@site/static/img/layout/padding/padding_code_snippet.png').default} alt="padding code example" style={{borderRadius: '12px', width: '100%'}}/>
</div>

### Try `.padding()` yourself!

```swift
struct PaddingModifier: View {
    var body: some View {
        VStack(spacing: 40) {
            Text("Your awesome text")
                .padding(16)
                .background(Color.purple.opacity(0.3))
            Text("Your awesome text no padding")
                .background(Color.purple.opacity(0.3))
        }
        .padding()
    }
}
```
