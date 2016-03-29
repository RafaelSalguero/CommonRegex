# CommonRegex

Regular expressions commonly used:

- Auto implemented C# property:
```
\s*{\s*get\s*\r\n\s*{\s*throw new NotImplementedException\(\);\s*}\s*set\s*{\s*throw new NotImplementedException\(\);\s*}\s*}
```

- C# Attribute
```
\[.*\]
```

- C# virtual property
```
(public|private)? (virtual) \w\S*\s\S*\s*{ get; set; }
```

###Convert C# to Typescript
**Convert single line numeric auto-properties:**

Replace:
```
public (int|decimal|float|double|long) (\S*) { get; set; }
```
With:
```
$2 : number;
```

**Convert single line DateTime auto-properties:**
Replace:
```
public DateTime (\S*) { get; set; }
```
With:
```
$1 : Date;
```

**Convert other single line auto-properties:**
Replace:
```
public (\S*) (\S*) { get; set; }
```
With:
```
$2 : $1;
```
