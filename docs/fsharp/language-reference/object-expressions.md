---
title: Objektausdrücke (F#)
description: Erfahren Sie, wie F#-Object-Ausdrücke verwenden, wenn Sie den zusätzlichen Code und zum Erstellen einer neuen erforderlichen Aufwand vermeiden möchten, mit dem Namen geben.
ms.date: 05/16/2016
ms.openlocfilehash: 1a971044d680d3bf5a6fff38affdaf001d5403b4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865461"
---
# <a name="object-expressions"></a><span data-ttu-id="63ff1-103">Objektausdrücke</span><span class="sxs-lookup"><span data-stu-id="63ff1-103">Object Expressions</span></span>

<span data-ttu-id="63ff1-104">Ein *Objekt Ausdruck* ist ein Ausdruck, der eine neue Instanz von einem dynamisch erstellten anonymen Objekttyps erstellt basiert auf einem vorhandenen Basistyp, Schnittstelle oder Satz von Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="63ff1-104">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>

## <a name="syntax"></a><span data-ttu-id="63ff1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="63ff1-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="63ff1-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="63ff1-106">Remarks</span></span>

<span data-ttu-id="63ff1-107">In der vorherigen Syntax wird die *Typename* darstellt, einen vorhandenen Klassen- oder Schnittstellentyp.</span><span class="sxs-lookup"><span data-stu-id="63ff1-107">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="63ff1-108">*Typ-Params* wird beschrieben, die optional generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="63ff1-108">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="63ff1-109">Die *Argumente* werden verwendet, nur für Klassentypen, die Konstruktorparameter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="63ff1-109">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="63ff1-110">Die *Memberdefinitionen* sind überschreibungen von Basisklassenmethoden oder Implementierungen von abstrakten Methoden von einer Basisklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="63ff1-110">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="63ff1-111">Das folgende Beispiel veranschaulicht verschiedene Arten von Object-Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="63ff1-111">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="63ff1-112">Verwenden von Object-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="63ff1-112">Using Object Expressions</span></span>

<span data-ttu-id="63ff1-113">Sie verwenden die Object-Ausdrücke, wenn Sie möchten, um zu vermeiden, die zusätzlichen Code und den Aufwand, die zum Erstellen einer neuen benannten Typ erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="63ff1-113">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="63ff1-114">Wenn Sie Object-Ausdrücke verwenden, um die Anzahl der in einem Programm erstellten Typen zu minimieren, können Sie reduzieren Sie die Anzahl von Codezeilen und zu verhindern, dass die unnötige die Verbreitung von Typen.</span><span class="sxs-lookup"><span data-stu-id="63ff1-114">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="63ff1-115">Anstatt zu erstellen, viele Typen nur, um bestimmte Situationen zu behandeln, können Sie einen Object-Ausdruck, der einen vorhandenen Typ anpasst, oder eine geeignete Implementierung der Schnittstelle für den speziellen Fall zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="63ff1-115">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>

## <a name="see-also"></a><span data-ttu-id="63ff1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63ff1-116">See also</span></span>

- [<span data-ttu-id="63ff1-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="63ff1-117">F# Language Reference</span></span>](index.md)
