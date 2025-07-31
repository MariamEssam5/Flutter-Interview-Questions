# 📗 Flutter "Difference Between" Questions & Answers (Basic to Advanced)

---

## 🟢 Basic Level

### 1. Difference between `StatelessWidget` and `StatefulWidget`
**Answer:**

| StatelessWidget                         | StatefulWidget                          |
|----------------------------------------|-----------------------------------------|
| UI does not change once built          | UI can change during runtime            |
| No `setState()` method                 | Uses `setState()` to rebuild UI         |
| Lightweight, better for performance    | Slightly heavier due to state handling  |
| Example: `Text`, `Icon`, `Container`   | Example: `Checkbox`, `TextField`        |

---

### 2. What’s the Difference between Mutable and Immutable objects ?

**Answer:**

| Feature              | Mutable Objects                                                            | Immutable Objects                                                         |
| -------------------- | -------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| **Definition**       | Objects whose **state or value can be changed** after they are created.    | Objects whose **state or value cannot be changed** once they are created. |
| **Change Behavior**  | Can update properties/fields directly.                                     | Cannot change properties; must create a new object.                       |
| **Memory**           | Typically requires **less memory** if updated repeatedly (same reference). | May create **new memory** allocation with each change.                    |
| **Examples in Dart** | Lists (`List`), Maps (`Map`), custom objects without `final`.              | `const` variables, `final` with immutable design, `String`.               |
| **Thread Safety**    | Not safe by default in multithreaded environments.                         | Safe because state doesn’t change.                                        |
| **Performance**      | Better for frequent updates.                                               | Better for predictable, safe, and stable data.                            |
| **Usage Scenario**   | Caches, collections that change often.                                     | App configuration, constants, keys.                                       |

### ✅ Mutable Example in Dart

```dart
List<String> names = ['Ali', 'Bavley'];
names.add('Sara');  // ✅ Allowed: names is mutable
```

### ❌ Immutable Example in Dart 

```dart
const List<String> names = ['Ali', 'Bavley'];
names.add('Sara'); // ❌ Error: Cannot modify an unmodifiable list

```

### ❄️ Immutable Object with final + const

```dart
class Person {
  final String name;
  const Person(this.name);
}

final p = Person('Ali');
// p.name = 'Sara'; // ❌ Not allowed: `name` is final

```

--- 

### 3. Difference between `var`, `final`, and `const`
**✅ Answer:**

| Keyword | Value Set At        | Mutable? | Use Case                         |
|---------|---------------------|----------|----------------------------------|
| `var`   | Runtime              | ✅ Yes   | When value changes               |
| `final` | Runtime (once only) | ❌ No    | Immutable after assignment       |
| `const` | Compile-time        | ❌ No    | Fixed at compile time            |

---

### 4. Difference between `Hot Reload` and `Hot Restart`
**✅ Answer:**

| Hot Reload                                | Hot Restart                                |
|-------------------------------------------|---------------------------------------------|
| Injects updated code into running app     | Rebuilds the app from scratch               |
| Keeps app state                           | Loses app state                             |
| Faster and more efficient for dev changes | Slower but useful for full app refresh      |

---

### 5. Difference between `final` and `const`
**✅ Answer:**

| final                        | const                               |
|-----------------------------|-------------------------------------|
| Set once at runtime         | Set at compile time only            |
| Can be assigned later       | Must be assigned immediately        |
| Good for runtime constants  | Good for fixed constants like colors|

---

### 6. Difference between `runApp()` and `main()`
**✅ Answer:**

| main()                             | runApp()                          |
|-----------------------------------|-----------------------------------|
| Entry point of the Dart program   | Launches the Flutter app          |
| Calls `runApp()` inside it        | Takes a widget as a parameter     |
| Just like `int main()` in C/C++   | Starts rendering widget tree      |

---

## 🟡 Intermediate Level

### 7. Difference between `push()` and `pushReplacement()`
**✅ Answer:**

| push()                                   | pushReplacement()                             |
|------------------------------------------|------------------------------------------------|
| Adds new route to navigation stack       | Replaces current route with a new one         |
| Can go back to previous screen           | Cannot go back to the replaced screen         |
| Used for normal navigation               | Used after login, onboarding, etc.            |

---

### 8. Difference between `push()` and `pushNamed()`
**✅ Answer:**

| push()                              | pushNamed()                                |
|------------------------------------|--------------------------------------------|
| Requires widget constructor        | Uses a named string route                  |
| Better for small-scale navigation  | Better for large apps with many routes     |
| Example: `push(context, ...)`      | Example: `pushNamed(context, '/home')`     |

---

### 9. Difference between `Expanded` and `Flexible`
**✅ Answer:**

| Expanded                              | Flexible                                   |
|---------------------------------------|---------------------------------------------|
| Takes all available space             | Takes portion of space based on `flex`     |
| Must expand to fill parent            | Can shrink or expand as needed             |
| Equivalent to `Flexible(fit: tight)`  | `fit` can be tight or loose                |

---

### 10. Difference between `ListView` and `ListView.builder`
**✅ Answer:**

| ListView                                  | ListView.builder                            |
|-------------------------------------------|----------------------------------------------|
| Builds all children at once               | Builds items lazily (on-demand)             |
| Good for small lists                      | Best for long/scrollable lists              |
| Less performant with many widgets         | More memory efficient                       |

---

### 11. Difference between `Future` and `Stream`
**✅ Answer:**

| Future                          | Stream                                 |
|----------------------------------|----------------------------------------|
| Asynchronous, returns once       | Emits multiple async values over time  |
| Use for single response          | Use for real-time or repeated updates  |
| Example: HTTP request            | Example: Chat messages, sockets        |

---

### 12. Difference between `Provider` and `BLoC`
**✅ Answer:**

| Provider                          | BLoC                                   |
|-----------------------------------|-----------------------------------------|
| Simpler, uses `ChangeNotifier`    | More complex, uses streams/sinks       |
| Good for small/medium apps        | Scalable for large projects            |
| Less boilerplate                  | More boilerplate but testable          |

---

### 13. Difference between `StatelessWidget`, `ConsumerWidget`, and `HookWidget`
**✅ Answer:**

| Widget Type       | Purpose                                              |
|-------------------|------------------------------------------------------|
| `StatelessWidget` | No state, standard Flutter widget                    |
| `ConsumerWidget`  | Reads providers without using `BuildContext`         |
| `HookWidget`      | Uses Flutter Hooks to simplify state & lifecycle     |

---

### 14. Difference between `late`, `nullable`, and `required`
**✅ Answer:**

| Keyword     | Description                                             |
|-------------|---------------------------------------------------------|
| `late`      | Initialized later, not null                             |
| `nullable`  | Variable can be null (`String? name`)                   |
| `required`  | Must pass this parameter at runtime                     |

---

### 15. Difference between `SharedPreferences`, `Hive`, and `SQLite`
**✅ Answer:**

| Tool              | Use Case                        | Type         |
|-------------------|----------------------------------|--------------|
| SharedPreferences | Store key-value small data       | Lightweight  |
| Hive              | NoSQL DB, better performance     | Lightweight  |
| SQLite            | Complex relational data storage  | Heavy-duty   |

---

