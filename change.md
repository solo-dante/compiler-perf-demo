# Make the following changes to the difference

- [Million.js blog](https://old.million.dev/blog/virtual-dom)
- In `vite.config.ts` make the following change

```diff
-    react({
-      babel: {
-        plugins: [["babel-plugin-react-compiler"]],
-      },
-    }),
+    react({
+      babel: {
+        //plugins: [["babel-plugin-react-compiler"]],
+      },
+    }),
```

- In `App.tsx` make the following change

```diff
+function SlowComponent(props: { unused?: any }) {
-function RealSlowComponent(props: { unused?: any }) {
```

```diff
+const SlowComponent = React.memo(RealSlowComponent)
```

- In `App.tsx` DemoComponent

```ts
const handleCounterClick = useCallback(() => {
  setCount((count) => count + 1);
});
```

```diff
- <CounterButton onClick={() => setCount((count) => count + 1)} />
+ <CounterButton onClick={handleCounterClick} />
```
