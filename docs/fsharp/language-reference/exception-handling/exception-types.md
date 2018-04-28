---
title: Ausnahmetypen (F#)
description: Informationen Sie zum Definieren und Verwenden von f#-Ausnahmetypen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 6aaa5cd1b94f829b98d5aed5dcf6e30472a8b751
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="exception-types"></a><span data-ttu-id="18e8e-103">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="18e8e-103">Exception Types</span></span>

<span data-ttu-id="18e8e-104">Es gibt zwei Kategorien von Ausnahmen in F# erläutert werden: .NET Ausnahmetypen und f#-Ausnahmetypen.</span><span class="sxs-lookup"><span data-stu-id="18e8e-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="18e8e-105">In diesem Thema wird beschrieben, wie zum Definieren und Verwenden von F#-Ausnahmetypen ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="18e8e-105">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="18e8e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="18e8e-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="18e8e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18e8e-107">Remarks</span></span>
<span data-ttu-id="18e8e-108">In der vorherigen Syntax *Ausnahmetyp* ist der Name, der einen neuen f#-Ausnahmetyp und *Argumenttyp* stellt den Typ eines Arguments, die beim Auslösen einer Ausnahme dieses Typs bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="18e8e-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="18e8e-109">Sie können mehrere Argumente angeben, mit der ein Tupel für *Argumenttyp*.</span><span class="sxs-lookup"><span data-stu-id="18e8e-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="18e8e-110">Eine typische Definition für eine f#-Ausnahme sieht ungefähr so aus.</span><span class="sxs-lookup"><span data-stu-id="18e8e-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="18e8e-111">Sie können eine Ausnahme dieses Typs generiert, mit der `raise` -Funktion wie folgt.</span><span class="sxs-lookup"><span data-stu-id="18e8e-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="18e8e-112">Können Sie einen f#-Ausnahmetyp direkt in den Filtern in einem `try...with` Ausdruck, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="18e8e-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="18e8e-113">Der Typ der Ausnahme, die Sie definieren, mit der `exception` -Schlüsselwort in f# ist eine neue Anwendungsart, die von erben `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="18e8e-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="18e8e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18e8e-114">See Also</span></span>
[<span data-ttu-id="18e8e-115">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="18e8e-115">Exception Handling</span></span>](index.md)

[<span data-ttu-id="18e8e-116">Ausnahmen: Die `raise`-Funktion</span><span class="sxs-lookup"><span data-stu-id="18e8e-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="18e8e-117">Ausnahmenhierarchie</span><span class="sxs-lookup"><span data-stu-id="18e8e-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
