---
title: Objektausdrücke
description: Erfahren Sie, wie Sie mit F# Objektausdrücke, wenn Sie die zusätzlichen Code und den Aufwand vermeiden möchten, erforderlich zum Erstellen einer neuen benannten Typ.
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157846"
---
# <a name="object-expressions"></a>Objektausdrücke

Ein *Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz von einem dynamisch erstellten anonymen Objekttyps erstellt basiert auf einem vorhandenen Basistyp, Schnittstelle oder Satz von Schnittstellen.

## <a name="syntax"></a>Syntax

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird die *Typename* darstellt, einen vorhandenen Klassen- oder Schnittstellentyp. *Typ-Params* wird beschrieben, die optional generischen Typparameter. Die *Argumente* werden verwendet, nur für Klassentypen, die Konstruktorparameter erforderlich ist. Die *Memberdefinitionen* sind überschreibungen von Basisklassenmethoden oder Implementierungen von abstrakten Methoden von einer Basisklasse oder Schnittstelle.

Das folgende Beispiel veranschaulicht verschiedene Arten von Object-Ausdrücke.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn "%A" obj1

// This object expression implements the IFormattable interface.
let delimiter(delim1: string, delim2: string, value: string) =
    { new System.IFormattable with
        member x.ToString(format: string, provider: System.IFormatProvider) =
            if format = "D" then
                delim1 + value + delim2
            else
                value }

let obj2 = delimiter("{","}", "Bananas!");

printfn "%A" (System.String.Format("{0:D}", obj2))

// Define two interfaces
type IFirst =
  abstract F : unit -> unit
  abstract G : unit -> unit

type ISecond =
  inherit IFirst
  abstract H : unit -> unit
  abstract J : unit -> unit

// This object expression implements both interfaces.
let implementer() =
    { new ISecond with
        member this.H() = ()
        member this.J() = ()
      interface IFirst with
        member this.F() = ()
        member this.G() = () }
```

## <a name="using-object-expressions"></a>Verwenden von Object-Ausdrücke

Sie verwenden die Object-Ausdrücke, wenn Sie möchten, um zu vermeiden, die zusätzlichen Code und den Aufwand, die zum Erstellen einer neuen benannten Typ erforderlich ist. Wenn Sie Object-Ausdrücke verwenden, um die Anzahl der in einem Programm erstellten Typen zu minimieren, können Sie reduzieren Sie die Anzahl von Codezeilen und zu verhindern, dass die unnötige die Verbreitung von Typen. Anstatt zu erstellen, viele Typen nur, um bestimmte Situationen zu behandeln, können Sie einen Object-Ausdruck, der einen vorhandenen Typ anpasst, oder eine geeignete Implementierung der Schnittstelle für den speziellen Fall zur Verfügung stellt.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
