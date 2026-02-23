# rn-onboarding-slides

A beautiful, fully customizable onboarding screen for React Native with **animated pagination dots**, smooth **swipe transitions**, and a **morphing next/start button**.

Built with `react-native-reanimated` for buttery-smooth 60fps animations running on the native thread.

---

<p align="center">
![Adobe Express - Screen Recording 2026-02-22 at 8 32 01 PM](https://github.com/user-attachments/assets/b7f0dee1-163d-4fd5-978c-ea507902f390)
</p>

---

### Customizable Animated Onboarding Component for React Native

A **beautiful, fully customizable onboarding screen component for React Native** featuring:

- ✨ Animated pagination dots  
- 🎬 Smooth swipe transitions  
- 🔘 Morphing next/start button  
- ⚡ 60fps native-thread animations powered by `react-native-reanimated`

Perfect for building modern **React Native onboarding screens**, intro slides, welcome screens, and feature walkthroughs.

---

## 📦 NPM Package

🔗 https://www.npmjs.com/package/rn-onboarding-slides  

```bash
npm install rn-onboarding-slides

## Installation

```bash
npm install rn-onboarding-slides
```

### Peer Dependencies

```bash
npm install react-native-reanimated expo-image
```

> Make sure to follow the [react-native-reanimated setup guide](https://docs.swmansion.com/react-native-reanimated/docs/fundamentals/getting-started/) to add Babel plugin and configure your app.

---

## Quick Start

```tsx
import { OnboardingScreen } from "rn-onboarding-slides";

const data = [
  {
    id: 1,
    image: require("./assets/slide1.jpg"),
    title: "Welcome",
    text: "The best app for sports fans",
  },
  {
    id: 2,
    image: require("./assets/slide2.jpg"),
    title: "Track Everything",
    text: "Follow your favorite teams live",
  },
  {
    id: 3,
    image: require("./assets/slide3.jpg"),
    title: "Get Started",
    text: "Join millions of fans today",
  },
];

export default function App() {
  return (
    <OnboardingScreen
      data={data}
      onPress={() => console.log("Onboarding done!")}
      buttonLabel="Get Started"
      showSkipButton
      onSkip={() => console.log("Skipped")}
    />
  );
}
```

---

## Theming & Customization

```tsx
<OnboardingScreen
  data={data}
  onPress={handleDone}
  buttonLabel="Let's Go"
  showSkipButton
  onSkip={handleSkip}
  skipLabel="Skip"
  theme={{
    // Dots
    dotActiveColor: "#FF6B6B",
    dotInactiveColor: "#555",
    dotActiveWidth: 24,
    dotHeight: 10,

    // Button
    buttonColor: "#FF6B6B",
    buttonTextColor: "#fff",
    buttonSize: 60,
    buttonFinalWidth: 150,
    buttonPosition: "right", // 'left' | 'right' | 'center'

    // Layout
    paginationPosition: "bottom-left", // 'bottom-left' | 'bottom-center' | 'bottom-right'
    backgroundColor: "#0a0a0a",
  }}
/>
```

---

## Custom Slide Rendering

Override the default slide layout completely using `renderItem`:

```tsx
<OnboardingScreen
  data={data}
  onPress={handleDone}
  renderItem={(item, index) => (
    <View style={{ flex: 1, alignItems: "center", justifyContent: "center" }}>
      <Image source={item.image} style={{ width: "100%", height: "70%" }} />
      <Text style={{ color: "#fff", fontSize: 24 }}>{item.title}</Text>
      <Text style={{ color: "#aaa", fontSize: 16 }}>{item.text}</Text>
    </View>
  )}
/>
```

---

## Props

| Prop             | Type                         | Default         | Description                              |
| ---------------- | ---------------------------- | --------------- | ---------------------------------------- |
| `data`           | `TOnboardingItem[]`          | **required**    | Array of slide data objects              |
| `onPress`        | `() => void`                 | **required**    | Called when last slide button is pressed |
| `buttonLabel`    | `string`                     | `'Get Started'` | Label shown on final slide button        |
| `showSkipButton` | `boolean`                    | `false`         | Whether to show a Skip button            |
| `onSkip`         | `() => void`                 | `undefined`     | Called when skip button is tapped        |
| `skipLabel`      | `string`                     | `'Skip'`        | Label for the skip button                |
| `theme`          | `TOnboardingTheme`           | see below       | Full theme/style customization           |
| `renderItem`     | `(item, index) => ReactNode` | `undefined`     | Custom slide renderer                    |
| `containerStyle` | `ViewStyle`                  | `undefined`     | Override outer container style           |

---

## TOnboardingItem

| Field   | Type                  | Description                             |
| ------- | --------------------- | --------------------------------------- |
| `id`    | `number`              | Unique identifier for the slide         |
| `image` | `ImageSourcePropType` | Slide background image (require or URI) |
| `title` | `string?`             | Optional slide title                    |
| `text`  | `string?`             | Optional slide description text         |

---

## Theme Options (TOnboardingTheme)

| Key                  | Type                                                 | Default         | Description                              |
| -------------------- | ---------------------------------------------------- | --------------- | ---------------------------------------- |
| `dotActiveColor`     | `string`                                             | `'#32CD32'`     | Active (current) dot color               |
| `dotInactiveColor`   | `string`                                             | `'#ccc'`        | Inactive dot color                       |
| `dotActiveWidth`     | `number`                                             | `20`            | Width of the active animated dot         |
| `dotHeight`          | `number`                                             | `10`            | Height of all dots                       |
| `buttonColor`        | `string`                                             | `'#32CD32'`     | Next/Start button background color       |
| `buttonTextColor`    | `string`                                             | `'#ffffff'`     | Button label color                       |
| `buttonSize`         | `number`                                             | `60`            | Button diameter in circular state        |
| `buttonFinalWidth`   | `number`                                             | `140`           | Button width when expanded on last slide |
| `buttonPosition`     | `'left' \| 'right' \| 'center'`                      | `'right'`       | Horizontal alignment of button           |
| `paginationPosition` | `'bottom-left' \| 'bottom-center' \| 'bottom-right'` | `'bottom-left'` | Alignment of pagination dots             |
| `backgroundColor`    | `string`                                             | `'#000000'`     | Screen background color                  |


---

## License

MIT © [Arbab Naseer](https://github.com/ArbabNaseer82)
