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
# <a name="object-expressions"></a><span data-ttu-id="aa3cf-103">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="aa3cf-103">Object Expressions</span></span>

<span data-ttu-id="aa3cf-104">Ein *Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz eines dynamisch erstellten, anonymen Objekt Typs erstellt, der auf einem vorhandenen Basistyp, einer Schnittstelle oder einem Satz von Schnittstellen basiert.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="aa3cf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa3cf-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="aa3cf-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="aa3cf-106">Remarks</span></span>

<span data-ttu-id="aa3cf-107">In der vorherigen Syntax stellt der *Typname* einen vorhandenen Klassentyp oder Schnittstellentyp dar.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="aa3cf-108">*Type-para* meters beschreibt die optionalen generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="aa3cf-109">Die *Argumente* werden nur für Klassentypen verwendet, die Konstruktorparameter erfordern.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="aa3cf-110">Die *Member-Definitionen* sind über schreibungen von Basisklassen Methoden oder Implementierungen von abstrakten Methoden aus einer Basisklasse oder einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="aa3cf-111">Im folgenden Beispiel werden verschiedene Typen von Objekt Ausdrücken veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-111">The following example illustrates several different types of object expressions.</span></span>

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

## <a name="using-object-expressions"></a><span data-ttu-id="aa3cf-112">Verwenden von Objekt Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="aa3cf-112">Using Object Expressions</span></span>

<span data-ttu-id="aa3cf-113">Sie verwenden Objekt Ausdrücke, wenn Sie zusätzlichen Code und mehr Aufwand für die Erstellung eines neuen benannten Typs vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="aa3cf-114">Wenn Sie Objekt Ausdrücke verwenden, um die Anzahl der in einem Programm erstellten Typen zu minimieren, können Sie die Anzahl der Codezeilen reduzieren und die unnötige Verbreitung von Typen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="aa3cf-115">Anstatt viele Typen zu erstellen, die nur für bestimmte Situationen geeignet sind, können Sie einen Objekt Ausdruck verwenden, der einen vorhandenen Typ anpasst oder eine entsprechende Implementierung einer Schnittstelle für den jeweiligen Fall bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="aa3cf-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa3cf-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa3cf-116">See also</span></span>

- [<span data-ttu-id="aa3cf-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="aa3cf-117">F# Language Reference</span></span>](index.md)
