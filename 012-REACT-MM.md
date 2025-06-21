# ⚛️ The Ultimate React Handbook

## ⭐ The Core Philosophy
- **"The UI Blueprint"**: Describe *what* your UI should look like with Components. React handles *how* to update the DOM efficiently.
- **Key Idea**: UI as a function of state (`UI = f(state)`).

## 1. Getting Started
- **Tool**: Vite (`npm create vite@latest`).
- **Entry Point**: `src/main.jsx` injects your app into `index.html`.
- **Root Component**: `src/App.jsx`.

## 2. The Building Blocks: Components & JSX
- **Component**: A reusable UI function. Must start with a capital letter.
- **JSX**: HTML-like syntax inside JavaScript.
  - **Syntax**: `const MyComponent = () => <h1>Hello</h1>;`
  - **Rules**: `className` not `class`. `{}` to embed JS expressions.

## 3. Passing Data: Props 🎁
- **Concept**: Parent-to-child data flow. Props are read-only.
- **Analogy**: Function arguments.
- **Syntax**:
  - **Parent**: `<ChildComponent name="Alice" />`
  - **Child**: `function ChildComponent(props) { return <h1>{props.name}</h1>; }`

## 4. Interactive Data: State (`useState`) 🧠
- **Concept**: Data a component manages itself. When state changes, the component re-renders.
- **Hook**: `useState`.
- **Syntax**: `const [value, setValue] = useState(initialValue);`
- **Example**: A counter where `setCount(count + 1)` triggers a re-render.

## 5. User Interaction: Events 🎬
- **Concept**: Handling user actions like clicks or input changes.
- **Syntax**: camelCase handlers (`onClick`, `onChange`).
- **Handler**: Pass a function: `<button onClick={myFunction}>`.
- **Pattern**: Controlled components for forms (state drives the input value).

## 6. Real-World Essentials
- ### Rendering Lists
  - **Method**: Use the `.map()` array method.
  - **`key` Prop**: Must provide a unique, stable `key` to each list item (`<li key={item.id}>`).
- ### Conditional Rendering
  - **If/Else**: Use a ternary operator (`{isLoggedIn ? <A /> : <B />}`).
  - **If/Then**: Use logical AND (`{hasMessages && <Notification />}`).
- ### Side Effects (`useEffect`)
  - **Concept**: For code that runs *after* render (data fetching, subscriptions).
  - **Syntax**: `useEffect(() => { /* effect code */ }, [dependencies]);`
  - **Dependency Array `[]`**: Runs the effect only once on mount.