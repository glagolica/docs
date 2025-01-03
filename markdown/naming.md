# Naming

File naming conventions are not strict when talking about file-based router crawling.
However there are small nuances when parsing markdown file names.

## Name Pattern

No matter the case of the file path, it will be converted to kebab-case:

```
/src/components/MyComponent.md     -->  GET /src/components/my-component
/src/nativeMain/kotlin/App.md      -->  GET /src/native-main/kotlin/app
/src/main.md                       -->  GET /src/main
/tests/Cases/Feature/LoginTest.md  -->  GET /tests/cases/feature/login-test
/my_project/__init__.md            -->  GET /my-project/init
```

...and so on.

## Internationalization

When translating documentation to more than few languages, developer is required to use suffix-syntax of file naming:

```
/src/components/MyComponent.en.md  -->  GET /en/src/components/my-component
/src/nativeMain/kotlin/App.ru.md   -->  GET /ru/src/native-main/kotlin/app
/src/main.md                       -->  GET /en/src/main
```

As stated above, Glagolica will use default language code to prepend in url if suffix is not provided.
Otherwise it will use the language code provided in the file name.

> [!NOTE]
> Glagolica only allows language codes from standardized [ISO 639](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) dictionary.
