# 📘 Flutter Interview Questions & Answers (From Basic to Advanced)

---

## 🟢 BASIC LEVEL

### 1. What is Flutter?
**Answer:**  
Flutter is an open-source UI toolkit developed by Google for building natively compiled applications for mobile, web, and desktop from a single codebase.

---

### 2. What language does Flutter use?
**Answer:**  
Flutter uses **Dart**, a client-optimized language developed by Google for fast apps on any platform.

---

### 3. What is the difference between `StatelessWidget` and `StatefulWidget`?
**Answer:**  
- `StatelessWidget`: UI does **not change** once built.
- `StatefulWidget`: UI **can change dynamically** during runtime using `setState()`.

---

### 4. What is a Widget in Flutter?
**Answer:**  
A widget is the **basic building block** of a Flutter UI. Everything in Flutter is a widget: layouts, text, images, buttons, etc.

---

### 5. What is hot reload?
**Answer:**  
Hot reload allows developers to inject updated source code files into a running Dart VM so changes reflect instantly without restarting the app.

---

### 6. What is the use of `pubspec.yaml`?
**Answer:**  
`pubspec.yaml` manages:
- Project metadata (name, description, version)
- Dependencies (plugins/packages)
- Assets (images, fonts)
- Environment settings

---

### 7. Difference between `final`, `const`, and `var`?
**Answer:**
- `var`: Variable whose type is inferred.
- `final`: Initialized only once; value set at runtime.
- `const`: Compile-time constant; deeply immutable.

---

### 8. What is `setState()` used for?
**Answer:**  
`setState()` tells Flutter that the internal state of a widget has changed and the UI should be rebuilt.

---

### 9. What are keys in Flutter?
**Answer:**  
Keys preserve state when widgets are moved within the widget tree. Useful in list views and performance optimizations.

---

### 10. How to create a simple layout in Flutter?
**Answer:**  
Using widgets like `Column`, `Row`, `Container`, `Padding`, etc.

```dart
Column(
  children: [
    Text('Hello'),
    ElevatedButton(onPressed: () {}, child: Text('Click')),
  ],
)
```````

## 🟡 INTERMEDIATE LEVEL

### 11. What is State Management?

**Answer:**  
State management is how you **handle data changes** and reflect them in the UI. Examples: `setState`, Provider, BLoC, Riverpod.

---

### 12. What is Provider and how does it work?

**Answer:**  
Provider is a wrapper around InheritedWidgets. It exposes data to widgets down the tree and rebuilds them when data changes.

---

### 13. What is BLoC?

**Answer:**  
**B**usiness **Lo**gic **C**omponent separates UI from business logic using Streams and Sinks. It’s useful in large scalable applications.

---

### 14. What is Navigator and how does routing work?

**Answer:**  
Navigator handles screen navigation using stack-based APIs.

```dart
Navigator.push(context, MaterialPageRoute(builder: (_) => NextPage()));
```

---
### 15. Difference between `pushNamed` and `push`?

**Answer:**

- `push`: Uses direct widget reference.

- `pushNamed`: Uses named route declared in `MaterialApp`.

---

### 16. How to make responsive UI?

**Answer:**

- Use `MediaQuery`, `LayoutBuilder`, and responsive widgets.

- Use `Expanded`, `Flexible`, `FittedBox`, and `Wrap`.
 ---
 
### 17. What is `Future`, `async`, and `await`?

**Answer:**  
Used for asynchronous operations.

```dart
Future<void> fetchData() async {
  var data = await http.get(Uri.parse('url'));
}
```