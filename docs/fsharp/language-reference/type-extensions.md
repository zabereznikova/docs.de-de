---
title: Typerweiterungen (F#)
description: Erfahren Sie, wie f# typerweiterungen erlauben, sich, dass Sie einen zuvor definierten Objekttyp neue Member hinzufügen.
ms.date: 05/16/2016
ms.openlocfilehash: 2181745ea75894fbfe35d5522c130baaf1876455
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566885"
---
# <a name="type-extensions"></a>Typerweiterungen

Mithilfe von Typerweiterungen können Sie einem zuvor definierten Objekttyp neue Member hinzufügen.

## <a name="syntax"></a>Syntax

```fsharp
// Intrinsic extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]

// Optional extension.
type typename with
    member self-identifier.member-name =
        body
    ...
[ end ]
```

## <a name="remarks"></a>Hinweise
Es gibt zwei Formen von Typerweiterungen, deren Syntax und Verhalten geringfügig voneinander abweichen. Ein *systeminterne Erweiterung* ist eine Erweiterung, die im gleichen Namespace oder Modul, in der gleichen Quelldatei und in der gleichen Assembly (DLL oder ausführbare Datei) angezeigt wird wie der Typ, der erweitert wird. Ein *optionale Erweiterung* ist eine Erweiterung, die außerhalb der ursprünglichen Moduls, Namespace oder Assembly des Typs, der zu vergrößernden angezeigt wird. Systeminterne Erweiterungen werden für einen Typ angezeigt, wenn der Typ durch Reflektion untersucht wird, nicht jedoch optionale Erweiterungen. Optionale Erweiterungen müssen in Modulen enthalten sein, und sie befinden sich nur im Gültigkeitsbereich, wenn das Modul, das die Erweiterung enthält, geöffnet ist.

In der vorherigen Syntax *Typename* stellt den Typ, der erweitert wird. Jeder Typ, auf den zugegriffen werden kann, ist erweiterbar, jedoch muss der Typname ein tatsächlicher Typname sein, keine Typabkürzung. Sie können in einer Typerweiterung mehrere Member definieren. Die *Selbstbezeichner* stellt die Instanz des Objekts aufgerufen wird, wie bei gewöhnlichen Membern.

Das `end`-Schlüsselwort ist in einfacher Syntax optional.

In Typerweiterungen definierte Member können genau wie andere Member eines Klassentyps verwendet werden. Wie andere Member können sie statische Member oder Instanzmember sein. Diese Methoden werden auch bezeichnet als *Erweiterungsmethoden*; Eigenschaften werden als bezeichnet *Erweiterungseigenschaften*und so weiter. Member optionaler Erweiterungen werden in statische Member kompiliert, für die die Objektinstanz implizit als erster Parameter übergeben wird. Sie verhalten sich jedoch so, als ob sie Instanzmember oder statische Member wären, entsprechend der Art ihrer Deklarierung. Member impliziter Erweiterungen werden als Member des Typs eingeschlossen, und sie können ohne Einschränkung verwendet werden.

Erweiterungsmethoden dürfen keine virtuellen oder abstrakten Methoden sein. Sie können andere Methoden des gleichen Namens überladen, aber der Compiler bevorzugt im Fall eines mehrdeutigen Aufrufs Nicht-Erweiterungsmethoden.

Wenn für einen Typ mehrere systeminterne Typerweiterungen vorhanden sind, müssen alle Member eindeutig sein. Bei optionalen Typerweiterungen können Member in unterschiedlichen Typerweiterungen, die auf den gleichen Typ erweitert werden, die gleichen Namen aufweisen. Mehrdeutigkeitsfehler treten nur auf, wenn Clientcode zwei unterschiedliche Gültigkeitsbereiche öffnet, die die gleichen Membernamen definieren.

Im folgenden Beispiel verfügt ein Typ in einem Modul über eine systeminterne Typerweiterung. Für Clientcode außerhalb des Moduls wird die Typerweiterung in jeder Hinsicht als regulärer Member des Typs dargestellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3701.fs)]

Sie können mithilfe von systeminternen Typerweiterungen die Definition eines Typs in Abschnitte aufteilen. Dies kann beim Verwalten umfangreicher Typdefinitionen hilfreich sein, um beispielsweise vom Compiler generierten Code und verfassten Code zu trennen oder um von verschiedenen Personen erstellten Code oder unterschiedlichen Funktionen zugeordneten Code in Gruppen zusammenzufassen.

Im folgenden Beispiel erweitert eine optionale Typerweiterung den `System.Int32`-Typ mit der Erweiterungsmethode `FromString`, die den statischen Member `Parse` aufruft. Die `testFromString`-Methode veranschaulicht, dass der neue Member wie ein beliebiger Instanzmember aufgerufen wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3702.fs)]

Der neue Instanzmember wird in IntelliSense wie eine beliebige andere Methode des `Int32`-Typs angezeigt, jedoch nur, wenn das Modul, das die Erweiterung enthält, geöffnet ist oder die Erweiterung aus einem anderen Grund im Gültigkeitsbereich ist.

## <a name="generic-extension-methods"></a>Generische Erweiterungsmethoden
Vor f# 3.1 unterstützte wurde im f#-Compiler unterstützt der Verwendung von c#-formaterweiterungsmethoden mit einer Variablen des generischen Typs, Arraytyps, Tupeltyps oder eines f#-Funktionstyps als "diesem" Parameter. F# 3.1 unterstützt die Verwendung dieser Erweiterungsmember.

Beispielsweise in F# 3.1-Code können Sie Erweiterungsmethoden mit Signaturen verwenden, die der folgenden Syntax in C# ähneln:

```csharp
static member Method<T>(this T input, T other)
```

Dieser Ansatz ist insbesondere dann sinnvoll, wenn der generische Typparameter eingeschränkt wird. Darüber hinaus können Sie Erweiterungsmember nun so in F#-Code deklarieren und einen zusätzlichen, semantisch umfangreichen Satz von Erweiterungsmethoden definieren. In F# definieren Sie normalerweise Erweiterungsmember, wie im folgenden Beispiel gezeigt:

```fsharp
open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq { for x in xs do for i in 1 .. n do yield x }
```

Für einen generischen Typ ist die Typvariable möglicherweise nicht beschränkt. Sie können einen C#-Formaterweiterungsmember in F# deklarieren, um diese Einschränkung zu umgehen. Wenn Sie diese Art der Deklaration mit der Inlinefunktion von F# kombinieren, können Sie generische Algorithmen als Erweiterungsmember darstellen.

Betrachten Sie hierzu die folgende Deklaration:

```fsharp
[<Extension>]
type ExtraCSharpStyleExtensionMethodsInFSharp () =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Mit dieser Deklaration können Sie Code schreiben, der dem folgenden Beispiel ähnelt.

```fsharp
let listOfIntegers = [ 1 .. 100 ]
let listOfBigIntegers = [ 1I to 100I ]
let sum1 = listOfIntegers.Sum()
let sum2 = listOfBigIntegers.Sum()
```

In diesem Code wird der gleiche generische arithmetische Code in Listen mit zwei Typen ohne Überladung angewendet, indem ein einzelner Erweiterungsmember definiert wird.


## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Mitglieder](members/index.md)
