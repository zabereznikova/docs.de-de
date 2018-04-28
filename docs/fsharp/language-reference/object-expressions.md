---
title: Objektausdrücke (F#)
description: Erfahren Sie, wie Objektausdrücke [F#] verwenden, wenn Sie den zusätzlichen Code und Mehraufwands für das Erstellen eines neuen vermeiden möchten benannten Typs dar.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f5a728823e7abe18aeb604b3991087fd0252698e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="object-expressions"></a><span data-ttu-id="7257d-103">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="7257d-103">Object Expressions</span></span>

<span data-ttu-id="7257d-104">Ein *-Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz eines Objekttyps dynamisch erstellte, anonymes, das erstellt wird basierend auf eine vorhandene Basistyp, eine Schnittstelle oder eine Gruppe von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="7257d-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="7257d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7257d-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="7257d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7257d-106">Remarks</span></span>
<span data-ttu-id="7257d-107">In der vorherigen Syntax der *Typename* einer vorhandenen Klassen- oder Schnittstellentyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="7257d-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="7257d-108">*Typ-Params* beschreibt die optionalen generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="7257d-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="7257d-109">Die *Argumente* werden nur für Klassentypen, die Konstruktorparameter erfordern verwendet.</span><span class="sxs-lookup"><span data-stu-id="7257d-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="7257d-110">Die *Memberdefinitionen* sind überschreibungen von Methoden der Basisklasse oder Implementierungen abstrakte Methoden aus einer Basisklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7257d-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="7257d-111">Das folgende Beispiel zeigt verschiedene Typen von Objektausdrücke.</span><span class="sxs-lookup"><span data-stu-id="7257d-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="7257d-112">Objektausdrücke verwenden</span><span class="sxs-lookup"><span data-stu-id="7257d-112">Using Object Expressions</span></span>
<span data-ttu-id="7257d-113">Objektausdrücke werden verwendet, wenn Sie möchten, um zu vermeiden, die zusätzlichen Code und den Aufwand, die zum Erstellen eines neuen benannten Typ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7257d-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="7257d-114">Wenn Sie Objektausdrücke verwenden, minimiert die Anzahl von Typen, die in einem Programm erstellt, können Sie reduzieren die Anzahl der Codezeilen und zu verhindern, dass der unnötige Vervielfältigung von Typen.</span><span class="sxs-lookup"><span data-stu-id="7257d-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="7257d-115">Statt viele Typen nur, um bestimmte Situationen zu bewältigen, können Sie ein Objektausdrücke, die einen vorhandenen Typ passt, oder stellt eine geeignete Implementierung einer Schnittstelle für den speziellen Fall zur hand.</span><span class="sxs-lookup"><span data-stu-id="7257d-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="7257d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7257d-116">See Also</span></span>
[<span data-ttu-id="7257d-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="7257d-117">F# Language Reference</span></span>](index.md)
