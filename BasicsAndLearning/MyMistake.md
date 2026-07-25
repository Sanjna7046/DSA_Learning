# C++ & STL Tips

## Check if a character is a digit

Instead of:

```cpp
if (s[i] >= '0' && s[i] <= '9')
```

Use:

```cpp
if (isdigit(s[i]))
```

---

## Find a substring in a string

Correct:

```cpp
while ((pos = s.find(s3)) != string::npos)
```

❌ Incorrect:

```cpp
while ((pos = s.find(s3)) != s.size())
```

> `string::npos` indicates that the substring was **not found**.

---

## Check for a substring

```cpp
if (s.substr(i, 5) == "mapie")
```

Checks whether the substring of length **5** starting at index `i` is `"mapie"`.

---

## Lambda Functions

```cpp
auto add = [&]() {
    // statements
};
```

### Explanation

- `auto` lets the compiler determine the function type.
- `[&]` captures all local variables **by reference**.
- The lambda can directly access and modify variables from the surrounding scope.

Example:

```cpp
int sum = 0;

auto add = [&](int x) {
    sum += x;
};

add(5);
cout << sum;   // 5
```

---

## Check if all elements are equal

```cpp
if (*min_element(a.begin(), a.end()) ==
    *max_element(a.begin(), a.end()))
{
    cout << "All same\n";
}

## Useful STL Functions

```cpp
sort(v.begin(), v.end());              // Ascending
sort(v.rbegin(), v.rend());            // Descending

reverse(v.begin(), v.end());

min_element(v.begin(), v.end());

max_element(v.begin(), v.end());

count(v.begin(), v.end(), x);

auto it = find(v.begin(), v.end(), 30);

if (it != v.end()) {
    cout << *it;      // 30
}

accumulate(v.begin(), v.end(), 0);

binary_search(v.begin(), v.end(), x);
```
