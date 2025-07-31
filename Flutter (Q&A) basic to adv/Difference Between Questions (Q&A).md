# 📗 Flutter "Difference Between" Questions & Answers (Basic to Intermediate)

---

## 🟢 Basic Level

### 1. ❓ Difference between `StatelessWidget` and `StatefulWidget`
**✅ Answer:**
| StatelessWidget                         | StatefulWidget                          |
|----------------------------------------|-----------------------------------------|
| UI does not change once built          | UI can change during runtime            |
| No `setState()` method                 | Uses `setState()` to rebuild UI         |
| Lightweight, better for performance    | Slightly heavier due to state handling  |
| Example: `Text`, `Icon`, `Container`   | Example: `Checkbox`, `TextField`        |

---

### 2. ❓ Difference between `var`, `final`, and `const`
**✅ Answer:**
| Keyword | Value Set At        | Mutable? | Use Case                         |
|---------|---------------------|----------|----------------------------------|
| `var`   | Runtime              | ✅ Yes   | When value changes               |
| `final` | Runtime (once only) | ❌ No    | Immutable after assignment       |
| `const` | Compile-time        | ❌ No    | Fixed at compile time            |

---

### 3. ❓ Difference between `Hot Reload` and `Hot Restart`
**✅ Answer:**
| Hot Reload                                | Hot Restart                                |
|-------------------------------------------|---------------------------------------------|
| Injects updated code into running app     | Rebuilds the app from scratch               |
| Keeps app state                           | Loses app state                             |
| Faster and more efficient for dev changes | Slower but useful for full app refresh      |

---

### 4. ❓ Difference between `final` and `const`
**✅ Answer:**
| final                        | const                               |
|-----------------------------|-------------------------------------|
| Set once at runtime         | Set at compile time only            |
| Can be assigned later       | Must be assigned immediately        |
| Good for runtime constants  | Good for fixed constants like colors|

---

### 5. ❓ Difference between `runApp()` and `main()`
**✅ Answer:**
| main()                             | runApp()                          |
|-----------------------------------|-----------------------------------|
| Entry point of the Dart program   | Launches the Flutter app          |
| Calls `runApp()` inside it        | Takes a widget as a parameter     |
| Just like `int main()` in C/C++   | Starts rendering widget tree      |

---

## 🟡 Intermediate Level

### 6. ❓ Difference between `push()` and `pushReplacement()`
**✅ Answer:**
| push()                                   | pushReplacement()                             |
|------------------------------------------|------------------------------------------------|
| Adds new route to navigation stack       | Replaces current route with a new one         |
| Can go back to previous screen           | Cannot go back to the replaced screen         |
| Used for normal navigation               | Used after login, onboarding, etc.            |

---

### 7. ❓ Difference between `push()` and `pushNamed()`
**✅ Answer:**
| push()                              | pushNamed()                                |
|------------------------------------|--------------------------------------------|
| Requires widget constructor        | Uses a named string route                  |
| Better for small-scale navigation  | Better for large apps with many routes     |
| Example: `push(context, ...)`      | Example: `pushNamed(context, '/home')`     |

---

### 8. ❓ Difference between `Expanded` and `Flexible`
**✅ Answer:**
| Expanded                              | Flexible                                   |
|---------------------------------------|---------------------------------------------|
| Takes all available space             | Takes portion of space based on `flex`     |
| Must expand to fill parent            | Can shrink or expand as needed             |
| Equivalent to `Flexible(fit: tight)`  | `fit` can be tight or loose                |

---

### 9. ❓ Difference between `ListView` and `ListView.builder`
**✅ Answer:**
| ListView                                  | ListView.builder                            |
|-------------------------------------------|----------------------------------------------|
| Builds all children at once               | Builds items lazily (on-demand)             |
| Good for small lists                      | Best for long/scrollable lists              |
| Less performant with many widgets         | More memory efficient                       |

---

### 10. ❓ Difference between `Future` and `Stream`
**✅ Answer:**
| Future                          | Stream                                 |
|----------------------------------|----------------------------------------|
| Asynchronous, returns once       | Emits multiple async values over time  |
| Use for single response          | Use for real-time or repeated updates  |
| Example: HTTP request            | Example: Chat messages, sockets        |

---

### 11. ❓ Difference between `Provider` and `BLoC`
**✅ Answer:**
| Provider                          | BLoC                                   |
|-----------------------------------|-----------------------------------------|
| Simpler, uses `ChangeNotifier`    | More complex, uses streams/sinks       |
| Good for small/medium apps        | Scalable for large projects            |
| Less boilerplate                  | More boilerplate but testable          |

---

### 12. ❓ Difference between `StatelessWidget`, `ConsumerWidget`, and `HookWidget`
**✅ Answer:**
| Widget Type       | Purpose                                              |
|-------------------|------------------------------------------------------|
| `StatelessWidget` | No state, standard Flutter widget                    |
| `ConsumerWidget`  | Reads providers without using `BuildContext`         |
| `HookWidget`      | Uses Flutter Hooks to simplify state & lifecycle     |

---

### 13. ❓ Difference between `late`, `nullable`, and `required`
**✅ Answer:**
| Keyword     | Description                                             |
|-------------|---------------------------------------------------------|
| `late`      | Initialized later, not null                             |
| `nullable`  | Variable can be null (`String? name`)                   |
| `required`  | Must pass this parameter at runtime                     |

---

### 14. ❓ Difference between `SharedPreferences`, `Hive`, and `SQLite`
**✅ Answer:**
| Tool              | Use Case                        | Type         |
|-------------------|----------------------------------|--------------|
| SharedPreferences | Store key-value small data       | Lightweight  |
| Hive              | NoSQL DB, better performance     | Lightweight  |
| SQLite            | Complex relational data storage  | Heavy-duty   |

---