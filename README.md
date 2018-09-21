# UniRx Tense

## What

* Provide `IObservable`, `IObserver` to handle tense.

## Requirement

* UniRx

## Install

```shell
yarn add "umm/unirx_tense#^1.0.0"
```

## Usage

### Notify tense

```csharp
var tenseSubject = new TenseSubject();
tenseSubject.WhenDo().Subscribe(_ => Debug.Log("`Do` notified"));
tenseSubject.WhenWill().Subscribe(_ => Debug.Log("`Will` notified"));
tenseSubject.WhenDid().Subscribe(_ => Debug.Log("`Did` notified"));

tenseSubject.Do(); // Notify `do`
tenseSubject.Will(); // Notify `will`
tenseSubject.Did(); // Notify `did`
```

### Notify tense with value

```csharp
var tenseSubject = new TenseSubject<int>();
tenseSubject.WhenDo().Subscribe(x => Debug.Log($"`Do` notified with value: {x}")); // `Do` notified with value: 1
tenseSubject.WhenWill().Subscribe(x => Debug.Log($"`Will` notified with value: {x}")); // `Will` notified with value: 2
tenseSubject.WhenDid().Subscribe(x => Debug.Log($"`Did` notified with value: {x}")); // `Did` notified with value: 3

tenseSubject.Do(1); // Notify `do`
tenseSubject.Will(2); // Notify `will`
tenseSubject.Did(3); // Notify `did`
```

## License

Copyright (c) 2018 Tetsuya Mori

Released under the MIT license, see [LICENSE.txt](LICENSE.txt)

