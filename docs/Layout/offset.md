---
id: offset
title: offset(_:)
sidebar_label: Offset
---

### What it is:

Moves a view’s content **without changing its original frame** - like sliding it around a glass pane, while the actual container stays put.

This is telling SwiftUI:

> "Keep the box where it is… but shift what’s inside by this much."

### Parameters:

- `offset:`: A CGSize with horizontal **(width)** and vertical **(height)** values
  - **Example**: `CGSize(width: 20, height: -10)` moves it 20 pts right and 10 pts up.

### When to use:

- You want to **nudge** a view around without breaking layout structure.
- You need **animations or transitions** where the views float in or out.
- You’re layering views and want precise control over **visual position**.
- You want to **show or hide something** subtly by sliding it in/out.

### Watch out for:

- The **original frame stays in place** — so layout boundaries won’t change.
- Stacking offsets can get messy — avoid piling on too many.
- It’s **not a substitute** for layout — **don’t use it to “fix” broken stacks**.

### `.offset(_:)` in action:

<div style={{marginLeft: '2rem', marginTop: '2rem', width: '80%'}}>
  <img src={require('@site/static/img/layout/offset/offset_animation.gif').default} alt="Frame animation example" style={{ width: '100%', borderRadius: '8px' }} />
</div>

### How it looks in Xcode:

<div style={{marginLeft: '2rem', marginTop: '2rem', width: '80%'}}>
  <img src={require('@site/static/img/layout/offset/offset.png').default} alt="Frame code example" style={{borderRadius: '12px', width: '100%'}}/>
</div>

### Try `.offset(_:)` yourself!

```swift
struct OffsetModifier: View {
    var body: some View {
        VStack(spacing: 40) {
            Text("Offset 0")
                .border(Color.gray)

            Text("Offset 20x, 25y")
                .border(Color.green)
                .offset(CGSize(width: 20, height: 25))
                .border(Color.red)
        }
    }
}
```
