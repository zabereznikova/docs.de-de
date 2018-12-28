---
title: Typerweiterungen
description: Erfahren Sie, wie F# typerweiterungen können Sie einen zuvor definierten Objekttyp neue Member hinzufügen.
ms.date: 07/20/2018
ms.openlocfilehash: 9c0c6247eb5b94e9f42377859026ba7b466eb2e4
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614057"
---
# <a name="type-extensions"></a>Erweiterungen des Typs

Erweiterungen des Typs (so genannte _Erweiterungen_) sind eine Familie von Funktionen, die Sie einem zuvor definierten Objekttyp neue Member hinzufügen können. Die drei Funktionen sind:

* Systeminterne typerweiterungen
* Optionalen typerweiterungen
* Erweiterungsmethoden

Jede kann in verschiedenen Szenarien verwendet werden und verfügt über unterschiedliche Kompromisse.

## <a name="syntax"></a>Syntax

```fsharp
// Intrinsic and optional extensions
type typename with
    member self-identifier.member-name =
        body
    ...

// Extension methods
open System.Runtime.CompilerServices

[<Extension>]
type Extensions() =
    [static] member self-identifier.extension-name (ty: typename, [args]) =
        body
    ...
```

## <a name="intrinsic-type-extensions"></a>Systeminterne typerweiterungen

Eine systeminterne typerweiterung ist eine Erweiterung, die einen benutzerdefinierten Typ erweitert.

Systeminterne typerweiterungen müssen definiert werden, in der gleichen Datei **und** im gleichen Namespace oder Modul wie der Typ, die sie erweitern können. Eine andere Definition führt dazu, ihnen wird [optionalen typerweiterungen](type-extensions.md#optional-type-extensions).

Systeminterne typerweiterungen sind manchmal eine bessere Möglichkeit zur Funktionalität von der Typdeklaration zu trennen. Das folgende Beispiel zeigt, wie Sie eine systeminterne typerweiterung definieren:

```fsharp
namespace Example

type Variant =
    | Num of int
    | Str of string
  
module Variant =
    let print v =
        match v with
        | Num n -> printf "Num %d" n
        | Str s -> printf "Str %s" s

// Add a member to Variant as an extension
type Variant with
    member x.Print() = Variant.print x
```

Mithilfe einer Erweiterung des Typs, können Sie jede der folgenden trennen:

* Die Deklaration einer `Variant` Typ
* Funktionen zum Drucken der `Variant` Klasse abhängig von der "Form"
* Eine Möglichkeit zum Zugriff auf die Drucken Funktionen mit Objekt-Stil `.`-Notation

Dies ist eine Alternative zum Definieren von alles, was als ein Element auf `Variant`. Obwohl dies nicht grundsätzlich besser ist, kann es eine übersichtlichere Darstellung der Funktionalität in einigen Situationen sein.

Systeminterne typerweiterungen werden als Member des Typs kompiliert, die Sie zu erweitern, die und für den Typ angezeigt wird, wenn der Typ durch Reflektion untersucht wird.

## <a name="optional-type-extensions"></a>Optionalen typerweiterungen

Eine optionale typerweiterung ist eine Erweiterung, die außerhalb der ursprünglichen Moduls, Namespace oder Assembly des Typs, der erweitert angezeigt wird.

Optionalen typerweiterungen eignen sich für die Erweiterung eines Typs, das Sie nicht selbst definiert haben. Zum Beispiel:

```fsharp
module Extensions

open System.Collections.Generic

type IEnumerable<'T> with
    /// Repeat each element of the sequence n times
    member xs.RepeatElements(n: int) =
        seq {
            for x in xs do
                for i in 1 .. n do
                    yield x
        }
```

Sie können jetzt zugreifen `RepeatElements` , als ob es sich um ein Mitglied ist <xref:System.Collections.Generic.IEnumerable%601> , solange die `Extensions` Modul wird geöffnet, in den Bereich, den Sie gerade arbeiten.

Optionale Erweiterungen werden nicht für den erweiterten Typ, wenn durch Reflektion untersucht angezeigt. Optionale Erweiterungen müssen in Modulen sein, und sie sind nur im Gültigkeitsbereich, wenn das Modul, das die Erweiterung enthält, geöffnet ist, oder andernfalls befindet sich im Bereich.

Member optionaler Erweiterungen werden in statische Member kompiliert, für die die Objektinstanz implizit als erster Parameter übergeben wird. Verhalten sich jedoch, als befänden sie Instanzmember oder statische Member nach, wie sie deklariert werden.

## <a name="generic-limitation-of-intrinsic-and-optional-type-extensions"></a>Generische Einschränkung der systeminterne und optionalen typerweiterungen

Es ist möglich, eine Erweiterung für einen generischen Typ deklarieren, in dem die Variable vom Typ beschränkt ist. Die Anforderung ist, dass die Einschränkung der Erweiterung einer Deklaration für die Einschränkung des deklarierten Typs entspricht.

Allerdings auch, wenn Einschränkungen zwischen einem deklarierten Typ und eine Erweiterung des Typs übereinstimmen, ist es möglich, für eine Einschränkung, die den Textkörper eines erweiterten Members abgeleitet werden, der andere Anforderungen für den Typparameter als den deklarierten Typ erzwingt. Zum Beispiel:

```fsharp
open System.Collections.Generic

// NOT POSSIBLE AND FAILS TO COMPILE!
//
// The member 'Sum' has a different requirement on 'T than the type IEnumerable<'T>
type IEnumerable<'T> with
    member this.Sum() = Seq.sum this
```

Es gibt keine Möglichkeit, dieser Code funktioniert mit der eine optionale typerweiterung abzurufen:

* Da ist, die `Sum` Member hat eine andere Einschränkung auf `'T` (`static member get_Zero` und `static member (+)`) als durch die Erweiterung festgelegt.
* Ändern die Erweiterung für die gleiche Einschränkung wie `Sum` entspricht die definierte Einschränkung nicht mehr auf `IEnumerable<'T>`.
* Vornehmen, ändern das Element zu `member inline Sum` gibt einen Fehler, dass die typeinschränkungen nicht übereinstimmt

Erwünscht sind statische Methoden, die "im Bereich" float"und können angezeigt werden, als ob sie einen Typ erweitern können. Dies ist, in denen Erweiterungsmethoden bereit, die erforderlich sind.

## <a name="extension-methods"></a>Erweiterungsmethoden

Schließlich können Erweiterungsmethoden (manchmal als "Erweiterungsmember des C#-Stil" bezeichnet) in F# als statische Membermethode in einer Klasse deklariert werden.

Erweiterungsmethoden sind nützlich für, wenn Sie Erweiterungen für einen generischen Typ definieren, die die Variable vom Typ eingeschränkt werden möchten. Zum Beispiel:

```fsharp
namespace Extensions

open System.Runtime.CompilerServices

[<Extension>]
type IEnumerableExtensions() =
    [<Extension>]
    static member inline Sum(xs: IEnumerable<'T>) = Seq.sum xs
```

Wenn verwendet, wird dieser Code machen es so aussieht, als ob `Sum` definiert ist, auf <xref:System.Collections.Generic.IEnumerable%601>, solange `Extensions` geöffnet wurde oder befindet sich im Bereich.

## <a name="other-remarks"></a>Andere Hinweise

Erweiterungen des Typs haben auch die folgenden Attribute:

* Jeder Typ, der zugegriffen werden kann, kann erweitert werden.
* Systeminterne und optionalen typerweiterungen können definieren, _alle_ Elementtyp, nicht nur Methoden. Daher sind Erweiterungseigenschaften auch möglich, z. B.
* Die `self-identifier` -Tokens in der [Syntax](type-extensions.md#syntax) stellt die Instanz des Typs aufgerufen wird, wie bei gewöhnlichen Membern.
* Erweiterte Mitglieder können statisch sein oder Instanzmember.
* Variablen für eine Erweiterung des Typs müssen es sich um die Einschränkungen des deklarierten Typs übereinstimmen.

Die folgenden Einschränkungen gelten auch für Erweiterungen des Typs:

* Erweiterungen des Typs unterstützen keine virtuelle oder abstrakte Methoden.
* Erweiterungen des Typs unterstützen keine Methoden zum Überschreiben als Erweiterungen.
* Erweiterungen des Typs unterstützen keine [Statisch aufgelöste Typparameter](generics/statically-resolved-type-parameters.md).
* Optionale Erweiterungen des Typs unterstützen keine Konstruktoren als Erweiterungen.
* Erweiterungen des Typs können nicht definiert werden [typabkürzungen](type-abbreviations.md).
* Erweiterungen des Typs gelten nicht für `byref<'T>` (auch wenn sie deklariert werden können).
* Erweiterungen des Typs gelten nicht für Attribute (auch wenn sie deklariert werden können).
* Sie können definieren, Erweiterungen, die andere Methoden, mit dem gleichen Namen zu überladen, aber F#-Compiler bevorzugt nicht-Erweiterungsmethoden gibt es ist ein Mehrdeutiger Aufruf.

Schließlich, wenn für einen Typ mehrere systeminterne typerweiterungen vorhanden ist, müssen alle Member eindeutig sein. Bei optionalen Typerweiterungen können Member in unterschiedlichen Typerweiterungen, die auf den gleichen Typ erweitert werden, die gleichen Namen aufweisen. Mehrdeutigkeitsfehler treten nur auf, wenn Clientcode zwei unterschiedliche Gültigkeitsbereiche öffnet, die die gleichen Membernamen definieren.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Mitglieder](members/index.md)