---
id: frame
title: frame(width:height:alginment:)
sidebar_label: Frame - Basic
---

### What it is:

Places a view inside a fixed-size invisible box - like forcing a view to live inside a custom-sized container.

Think of it as telling SwiftUI:

> "This view must be exactly this wide/tall - no matter what it wants."

### Parameters:

- `width`: How wide do you want the view to be? If you leave it out, SwiftUI picks the width.
- `height`: Same idea - if you don't set it, SwiftUI lets the view decide its own height.
- `alignment`: This tells SwiftUI where inside the frame the content should sit. It only matters when the frame is bigger than the view.

### When to use:

- You want to give your view a specific width and/or height.
- You’re building precise UI layouts or grids.
- You want to control alignment of a view inside a container.
- You’re combining it with **.background()** or **.border()** and need tight control over sizing.

### Watch out for:

- If you leave **width** or **height** as **nil**, SwiftUI uses this view’s natural size in that dimension
- The alignment only matters when the **frame is larger than the content** - otherwise, it’s ignored.
- Stacking **.frame()** with other **layout** modifiers (like [**.padding()**](./padding.md) or **.offset()**) can cause unexpected shifts if the order isn’t clear.

### `.frame(width:height:alginment:)` in action:

<div style={{marginLeft: '2rem', marginTop: '2rem', width: '80%'}}>
  <img src={require('@site/static/img/layout/frame_basic/frame_basic_animation.gif').default} alt="Frame animation example" style={{ width: '100%', borderRadius: '8px' }} />
</div>

### How it looks in Xcode:

<div style={{marginLeft: '2rem', marginTop: '2rem', width: '80%'}}>
  <img src={require('@site/static/img/layout/frame_basic/frame_basic.png').default} alt="Frame code example" style={{borderRadius: '12px', width: '100%'}}/>
</div>

### Try `.frame(width:height:alignment:)` yourself!

```swift
struct FrameModifier: View {
    var body: some View {
        VStack(spacing: 20) {
            Text("Framed text")
                .frame(width: 300, height: 50, alignment: .topTrailing)
                .background(Color.purple.opacity(0.3))

            Text("Purple Rectangle")
                .frame(width: 200, height: 100)
                .background(Color.purple.opacity(0.3))

            Text("Only fixed height")
                .frame(height: 100)
                .background(Color.blue.opacity(0.3))

            Text("Aligned top-leading")
                .frame(width: 200, height: 30, alignment: .topLeading)
                .background(Color.red.opacity(0.3))
        }
    }
}
```
