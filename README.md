# CommonRegex

Regular expressions commonly used:

- Auto implemented C# property:
```
\s*{\s*get\s*\r\n\s*{\s*throw new NotImplementedException\(\);\s*}\s*set\s*{\s*throw new NotImplementedException\(\);\s*}\s*}
```

`To implement replace with:`
```
 { get; set; }
```

- C# Attribute
```
\[.*\]
```

- C# virtual property
```
(public|private)? (virtual) \w\S*\s\S*\s*{ get; set; }
```

###Convert C# to Typescript *(Search-Replace pairs)*
**Convert single line numeric auto-properties:**

```
public (int|decimal|float|double|long) (\S*) { get; set; }
```
```
$2 : number;
```

**Convert single line DateTime auto-properties:**
```
public DateTime (\S*) { get; set; }
```
```
$1 : Date;
```

**Convert other single line auto-properties:**
```
public (\S*) (\S*) { get; set; }
```
```
$2 : $1;
```
