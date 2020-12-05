---
title: Objektausdrücke
description: 'Erfahren Sie, wie Sie F #-Objekt Ausdrücke verwenden, um den zusätzlichen Code und Aufwand zu vermeiden, der zum Erstellen eines neuen benannten Typs erforderlich ist.'
ms.date: 02/08/2019
ms.openlocfilehash: 8a3e40b7833b551eefb95ec62b935acd1ba7b1f9
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740301"
---
# <a name="object-expressions"></a>Objektausdrücke

Ein *Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz eines dynamisch erstellten, anonymen Objekt Typs erstellt, der auf einem vorhandenen Basistyp, einer Schnittstelle oder einem Satz von Schnittstellen basiert.

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

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax stellt der *Typname* einen vorhandenen Klassentyp oder Schnittstellentyp dar. *Type-para* meters beschreibt die optionalen generischen Typparameter. Die *Argumente* werden nur für Klassentypen verwendet, die Konstruktorparameter erfordern. Die *Member-Definitionen* sind über schreibungen von Basisklassen Methoden oder Implementierungen von abstrakten Methoden aus einer Basisklasse oder einer Schnittstelle.

Im folgenden Beispiel werden verschiedene Typen von Objekt Ausdrücken veranschaulicht.

```fsharp
// This object expression specifies a System.Object but overrides the
// ToString method.
let obj1 = { new System.Object() with member x.ToString() = "F#" }
printfn $"{obj1}"

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

## <a name="using-object-expressions"></a>Verwenden von Objekt Ausdrücken

Sie verwenden Objekt Ausdrücke, wenn Sie zusätzlichen Code und mehr Aufwand für die Erstellung eines neuen benannten Typs vermeiden möchten. Wenn Sie Objekt Ausdrücke verwenden, um die Anzahl der in einem Programm erstellten Typen zu minimieren, können Sie die Anzahl der Codezeilen reduzieren und die unnötige Verbreitung von Typen vermeiden. Anstatt viele Typen zu erstellen, die nur für bestimmte Situationen geeignet sind, können Sie einen Objekt Ausdruck verwenden, der einen vorhandenen Typ anpasst oder eine entsprechende Implementierung einer Schnittstelle für den jeweiligen Fall bereitstellt.

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
