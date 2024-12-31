# Frontend Bundling

To bundle web frontend part of Glagolica in the executable, we use `lz4hc -9` compression.

When starting Glagolica, binary automatically decompresses the bundle to the temporary folder under versioned directory.

For Windows it is:

```
C:\Users\<username>\AppData\Local\Temp\.glagolica\1.0.0
```

For MacOS & Linux it is:

```
/tmp/.glagolica/1.0.0
```

> [!NOTE]
> It is safe to delete decompressed bundle when Glagolica instance is killed.
