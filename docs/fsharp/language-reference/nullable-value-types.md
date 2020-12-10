---
title: Auf NULL festlegbare Werttypen
description: 'Erfahren Sie, wie Sie auf NULL festleg Bare Werttypen, eine Möglichkeit zur Darstellung von Werttypen, die auch NULL sein können, in F # verwenden.'
ms.date: 11/19/2020
ms.openlocfilehash: e28cbfc57c5631573f46ac36462517cf011e96d2
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009637"
---
# <a name="nullable-value-types"></a>Auf NULL festlegbare Werttypen

Ein auf NULL festleg _barer Werttyp_ `Nullable<'T>` stellt einen beliebigen Strukturtyp dar, der auch sein könnte [](structures.md) `null` Dies ist hilfreich, wenn Sie mit Bibliotheken und Komponenten interagieren, die diese Arten von Typen, wie z. b. ganze Zahlen, mit einem `null` Wert aus Effizienzgründen darstellen können. Der zugrunde liegende Typ, der dieses Konstrukt unterstützt, ist <xref:System.Nullable%601?displayProperty=nameWithType> .

## <a name="syntax"></a>Syntax

```fsharp
Nullable<'T>
Nullable value
```

## <a name="declare-and-assign-with-values"></a>Deklarieren und mit Werten zuweisen

Das Deklarieren eines auf NULL festleg baren Werttyps ist wie das Deklarieren eines beliebigen Wrapper ähnlichen Typs in F #:

```fsharp
open System

let x = 12
let nullableX = Nullable<int> x
```

Sie können auch den generischen Typparameter entfernen und den Typrückschluss zulassen, um ihn aufzulösen:

```fsharp
open System

let x = 12
let nullableX = Nullable x
```

Wenn Sie einem Werttyp, der NULL-Werte zulässt, zuweisen möchten, müssen Sie auch explizit sein. Es gibt keine implizite Konvertierung für F #-definierte Werttypen, die NULL-Werte zulassen:

```fsharp
open System

let mutable x = Nullable 12
x <- Nullable 13
```

## <a name="assign-null"></a>NULL zuweisen

Sie können `null` einem Werttyp, der NULL-Werte zulässt, nicht direkt zuweisen Verwenden Sie `Nullable()` stattdessen:

```fsharp
let mutable a = Nullable 42
a <- Nullable()
```

Der Grund hierfür ist, dass `Nullable<'T>` nicht über `null` einen geeigneten Wert verfügt.

## <a name="pass-and-assign-to-members"></a>Übergeben und zuweisen an Member

Ein wichtiger Unterschied zwischen der Arbeit mit Membern und F #-Werten besteht darin, dass Werte zulässt-Werttypen implizit abgeleitet werden können, wenn Sie mit Membern arbeiten. Beachten Sie die folgende Methode, die einen auf NULL festleg baren Werttyp als Eingabe annimmt:

```fsharp
type C() =
    member _.M(x: Nullable<int>) = x.HasValue
    member val NVT = Nullable 12 with get, set

let c = C()
c.M(12)
c.NVT <- 12
```

Im vorherigen Beispiel können Sie `12` an die-Methode übergeben `M` . Sie können auch `12` der Auto-Eigenschaft zuweisen `NVT` . Wenn die Eingabe als Werte zulässt-Werttyp erstellt werden kann und mit dem Zieltyp übereinstimmt, konvertiert der F #-Compiler solche Aufrufe oder Zuweisungen implizit.

## <a name="examine-a-nullable-value-type-instance"></a>Überprüfen einer Instanz, die NULL-Werte zulässt

Anders als bei [Optionen](options.md), bei denen es sich um ein generalisiertes Konstrukt zur Darstellung eines möglichen Werts handelt, werden Werte zulässt-Werttypen nicht mit Musterabgleich verwendet Stattdessen müssen Sie einen [`if`](conditional-expressions-if-then-else.md) Ausdruck verwenden und die-Eigenschaft überprüfen `HasValue` .

Um den zugrunde liegenden Wert zu erhalten, verwenden Sie die- `Value` Eigenschaft nach einer `HasValue` Überprüfung wie folgt:

```fsharp
open System

let a = Nullable 42

if a.HasValue then
    printfn $"{a} is {a.Value}"
else
    printfn $"{a} has no value."
```

## <a name="nullable-operators"></a>NULL-Werte zulassen

Vorgänge für Werttypen, die NULL-Werte zulassen, wie z. b. Arithmetik oder Vergleiche, können die Verwendung von [NULL-Werten](symbol-and-operator-reference/nullable-operators.md)zulassen

Mithilfe von Konvertierungs Operatoren aus dem-Namespace können Sie von einem Werte zulässt-Werttyp in einen anderen konvertieren `FSharp.Linq` :

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt
```

Sie können auch einen geeigneten Operator, der keine NULL-Werte zulässt, verwenden, um einen primitiven Typ zu konvertieren, der eine Ausnahme auslöst, wenn er über keinen Wert verfügt:

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

printfn $"value is %f{float nullableFloat}"
```

Sie können auch die Operatoren, die NULL-Werte zulassen, zum Überprüfen von `HasValue` und verwenden `Value` :

```fsharp
open System
open FSharp.Linq

let nullableInt = Nullable 10
let nullableFloat = Nullable.float nullableInt

let isBigger = nullableFloat ?> 1.0
let isBiggerLongForm = nullableFloat.HasValue && nullableFloat.Value > 1.0
```

Der `?>` Vergleich überprüft, ob die linke Seite NULL-Werte zulässt und nur erfolgreich ist, wenn Sie über einen Wert verfügt. Dies entspricht der folgenden Zeile.

## <a name="see-also"></a>Weitere Informationen

- [Strukturen](structures.md)
- [F #-Optionen](options.md)
