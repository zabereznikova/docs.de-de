---
title: Objektausdrücke
description: Erfahren Sie, wie Sie mit F# Objektausdrücke, wenn Sie die zusätzlichen Code und den Aufwand vermeiden möchten, erforderlich zum Erstellen einer neuen benannten Typ.
ms.date: 02/08/2019
ms.openlocfilehash: 63f2c1d7128721b7b8c744e4cf02d73c2a8b4a07
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157846"
---
# <a name="object-expressions"></a><span data-ttu-id="c1d2d-103">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="c1d2d-103">Object Expressions</span></span>

<span data-ttu-id="c1d2d-104">Ein *Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz von einem dynamisch erstellten anonymen Objekttyps erstellt basiert auf einem vorhandenen Basistyp, Schnittstelle oder Satz von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="c1d2d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1d2d-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="c1d2d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1d2d-106">Remarks</span></span>

<span data-ttu-id="c1d2d-107">In der vorherigen Syntax wird die *Typename* darstellt, einen vorhandenen Klassen- oder Schnittstellentyp.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="c1d2d-108">*Typ-Params* wird beschrieben, die optional generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="c1d2d-109">Die *Argumente* werden verwendet, nur für Klassentypen, die Konstruktorparameter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="c1d2d-110">Die *Memberdefinitionen* sind überschreibungen von Basisklassenmethoden oder Implementierungen von abstrakten Methoden von einer Basisklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="c1d2d-111">Das folgende Beispiel veranschaulicht verschiedene Arten von Object-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-111">The following example illustrates several different types of object expressions.</span></span>

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

## <a name="using-object-expressions"></a><span data-ttu-id="c1d2d-112">Verwenden von Object-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c1d2d-112">Using Object Expressions</span></span>

<span data-ttu-id="c1d2d-113">Sie verwenden die Object-Ausdrücke, wenn Sie möchten, um zu vermeiden, die zusätzlichen Code und den Aufwand, die zum Erstellen einer neuen benannten Typ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="c1d2d-114">Wenn Sie Object-Ausdrücke verwenden, um die Anzahl der in einem Programm erstellten Typen zu minimieren, können Sie reduzieren Sie die Anzahl von Codezeilen und zu verhindern, dass die unnötige die Verbreitung von Typen.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="c1d2d-115">Anstatt zu erstellen, viele Typen nur, um bestimmte Situationen zu behandeln, können Sie einen Object-Ausdruck, der einen vorhandenen Typ anpasst, oder eine geeignete Implementierung der Schnittstelle für den speziellen Fall zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="c1d2d-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1d2d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1d2d-116">See also</span></span>

- [<span data-ttu-id="c1d2d-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="c1d2d-117">F# Language Reference</span></span>](index.md)
