# Chapter 3 — Styling + Flexbox

**Status:** 🟢 COMPLETE

> Styling is intentionally kept to practical essentials; detailed styling can be handled when a specific UI problem requires it.

---

## 1. Covered in This Chapter

- `style` prop
- `StyleSheet.create()`
- Flexbox main/cross axes
- `flexDirection`
- `justifyContent`
- `alignItems`
- `flexWrap`
- `gap`
- `padding`
- `margin`

---

## 2. The `style` Prop

```jsx
<Text style={{ fontSize: 24 }}>
  Foodie
</Text>
```

---

## 3. `StyleSheet.create()`

```jsx
const styles = StyleSheet.create({
  title: {
    fontSize: 24,
    fontWeight: 'bold',
  },
});
```

Then:

```jsx
<Text style={styles.title}>Foodie</Text>
```

```mermaid
flowchart LR
    A["Inline style object { }"] -.->|"quick, one-off"| C[Rendered UI]
    B["StyleSheet.create({...})"] -->|"reusable, organized"| C
```

---

## 4. Flexbox Mental Model

```mermaid
flowchart TD
    A[flexDirection] --> B["Determines MAIN AXIS"]
    B --> C[justifyContent]
    B --> D[alignItems]
    C --> E["Positions along MAIN AXIS"]
    D --> F["Positions along CROSS AXIS"]
```

### React Native's Default

```mermaid
flowchart LR
    A["flexDirection: column (default)"] --> B["Main axis = vertical ↕"]
    A --> C["Cross axis = horizontal ↔"]
```

### With `row`

```mermaid
flowchart LR
    A["flexDirection: row"] --> B["Main axis = horizontal ↔"]
    A --> C["Cross axis = vertical ↕"]
```

| `flexDirection` | Main Axis | Cross Axis |
|---|---|---|
| `column` (default) | Vertical ↕ | Horizontal ↔ |
| `row` | Horizontal ↔ | Vertical ↕ |

---

## 5. Layout Properties

| Property | Effect |
|---|---|
| `justifyContent` | Positions children on the **main axis** |
| `alignItems` | Positions children on the **cross axis** |
| `flexWrap: 'wrap'` | Allows children onto another line |
| `gap` | Creates space **between** flex children |
| `padding` | Space **inside** an element |
| `margin` | Space **outside** an element |

### Padding vs Margin

```mermaid
flowchart TD
    subgraph Margin["margin — space OUTSIDE"]
        direction TB
        subgraph Box["Element"]
            subgraph Padding["padding — space INSIDE"]
                Content["Content"]
            end
        end
    end
```

---

## 6. Core Mental Model

```mermaid
flowchart TD
    A[style] --> A1["Controls appearance / layout"]
    B[flexDirection] --> B1["Determines MAIN AXIS"]
    C[justifyContent] --> C1["Positions along MAIN AXIS"]
    D[alignItems] --> D1["Positions along CROSS AXIS"]
    E[flexWrap] --> E1["Allows children onto another line"]
    F[padding] --> F1["Space INSIDE"]
    G[margin] --> G1["Space OUTSIDE"]
    H[gap] --> H1["Space BETWEEN children"]
```

| Concept | Core Idea |
|---|---|
| `style` | Controls appearance/layout |
| `flexDirection` | Determines **main axis** |
| `justifyContent` | Positions along **main axis** |
| `alignItems` | Positions along **cross axis** |
| `flexWrap` | Allows children onto another line |
| `padding` | Space **inside** |
| `margin` | Space **outside** |
| `gap` | Space **between** children |

---

## ✅ Recall Checklist

- [ ] Difference between inline `style` and `StyleSheet.create()`
- [ ] What determines the main axis vs the cross axis
- [ ] What `justifyContent` controls vs `alignItems`
- [ ] What `flexWrap: 'wrap'` does
- [ ] Difference between `padding`, `margin`, and `gap`
- [ ] Default `flexDirection` in React Native and what axes it produces

---

## 🎯 Chapter 3 Complete

```mermaid
flowchart TD
    A[style prop] --> B[StyleSheet.create]
    B --> C[flexDirection → Main Axis]
    C --> D[justifyContent + alignItems]
    D --> E[flexWrap]
    E --> F[padding / margin / gap]
```
