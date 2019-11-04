---
title: Statisch aufgelöste Typparameter
description: Erfahren Sie, wie ein F# statisch aufgelöster Typparameter verwendet wird, der zur Kompilierzeit anstelle der Laufzeit durch einen tatsächlichen Typ ersetzt wird.
ms.date: 05/16/2016
ms.openlocfilehash: 017c18dd3caaa484ddc653557573f548e3224ca0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424999"
---
# <a name="statically-resolved-type-parameters"></a>Statisch aufgelöste Typparameter

Ein *statisch aufgelöster Typparameter* ist ein Typparameter, der zur Kompilierzeit anstelle der Laufzeit durch einen tatsächlichen Typ ersetzt wird. Ihnen wird ein Caretzeichen (^) vorangestellt.

## <a name="syntax"></a>Syntax

```fsharp
ˆtype-parameter
```

## <a name="remarks"></a>Hinweise

In der Programmiersprache F# gibt es zwei unterschiedliche Arten von Typparametern. Die erste Art ist der standardmäßige generische Typparameter. Diese werden durch ein Apostroph (') angegeben, wie bei `'T` und `'U`. Sie entsprechen generischen Typparametern in anderen .NET Framework-Sprachen. Die andere Art ist statisch aufgelöst und wird von einem Caretzeichensymbol, wie in `^T` und `^U`.

Statisch aufgelöste Typparameter sind hauptsächlich in Verbindung mit Membereinschränkungen nützlich, die Ihnen die Angabe ermöglichen, dass ein Typargument zur Verwendung einen bestimmten Member oder mehrere Member aufweisen muss. Es gibt keine Möglichkeit, diese Art von Einschränkung mit einem regulären generischen Typparameter zu erstellen.

In der folgenden Tabelle werden die Ähnlichkeiten und die Unterschiede zwischen den beiden Arten von Typparametern zusammengefasst.

|Feature|Generisch|Statisch aufgelöst|
|-------|-------|-------------------|
|Syntax|`'T`, `'U`|`^T`, `^U`|
|Auflösungszeit|Laufzeit|Kompilierungsfehler|
|Member-Einschränkungen|Kann nicht mit Membereinschränkungen verwendet werden.|Kann mit Membereinschränkungen verwendet werden.|
|Codeerzeugung|Ein Typ (oder eine Methode) mit standardmäßigen generischen Typparametern führt zur Erstellung eines einzelnen generischen Typs oder einer Methode.|Mehrere Instanziierungen von Typen und Methoden werden generiert, einer für jeden erforderlichen Typ.|
|Verwendung mit Typen|Kann mit Typen verwendet werden.|Kann nicht mit Typen verwendet werden.|
|Verwendung mit Inlinefunktionen|Nein. Eine Inlinefunktion kann nicht mit einem standardmäßigen generischen Typparameter parametrisiert werden.|Ja. Statisch aufgelöste Typparameter können nicht auf Funktionen oder Methoden angewendet werden, die nicht inline sind.|

Viele F#-Kernbibliotheksfunktionen, besonders Operatoren, verfügen über statisch aufgelöste Typparameter. Diese Funktionen und die Operatoren sind inline, und ergeben effiziente Codeerstellung für numerische Berechnungen.

Inlinemethoden und -funktionen, die Operatoren oder andere Funktionen mit statisch aufgelösten Typparametern verwenden, können auch selbst statisch aufgelöste Typparameter verwenden. Oft leitet der Typrückschluss ab, dass solche Inlinefunktionen statisch aufgelöste Typparameter aufweisen. Im folgenden Beispiel wird eine Operatordefinition veranschaulicht, die so abgeleitet wird, dass sie einen statisch aufgelösten Typparameter hat.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

Der aufgelöste Typ von `(+@)` basiert auf der Verwendung von `(+)` und `(*)`, durch die vom Typrückschluss Membereinschränkungen für die statisch aufgelösten Typparameter abgeleitet werden. Der aufgelöste Typ, wie im F#-Interpreter angezeigt, lautet wie folgt.

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

Die Ausgabe lautet wie folgt.

```console
2
1.500000
```

Ab F# 4,1 können Sie auch konkrete Typnamen in statisch aufgelösten Typparameter Signaturen angeben.  In früheren Versionen der Sprache konnte der Typname tatsächlich vom Compiler abgeleitet werden, konnte aber nicht in der Signatur angegeben werden.  Ab F# 4,1 können Sie auch konkrete Typnamen in statisch aufgelösten Typparameter Signaturen angeben. Im Folgenden ein Beispiel:

```fsharp
let inline konst x _ = x

type CFunctor() =
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a>Siehe auch

- [Generics](index.md)
- [Typableitung](../type-inference.md)
- [Automatische Verallgemeinerung](automatic-generalization.md)
- [Einschränkungen](constraints.md)
- [Inlinefunktionen](../functions/inline-functions.md)
