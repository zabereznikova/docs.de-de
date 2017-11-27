---
title: Ausnahmetypen (F#)
description: Informationen Sie zum Definieren und Verwenden von f#-Ausnahmetypen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="exception-types"></a><span data-ttu-id="5afb2-104">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="5afb2-104">Exception Types</span></span>

<span data-ttu-id="5afb2-105">Es gibt zwei Kategorien von Ausnahmen in F# erläutert werden: .NET Ausnahmetypen und f#-Ausnahmetypen.</span><span class="sxs-lookup"><span data-stu-id="5afb2-105">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="5afb2-106">In diesem Thema wird beschrieben, wie zum Definieren und Verwenden von F#-Ausnahmetypen ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="5afb2-106">This topic describes how to define and use F# exception types.</span></span>


## <a name="syntax"></a><span data-ttu-id="5afb2-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5afb2-107">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="5afb2-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5afb2-108">Remarks</span></span>
<span data-ttu-id="5afb2-109">In der vorherigen Syntax *Ausnahmetyp* ist der Name, der einen neuen f#-Ausnahmetyp und *Argumenttyp* stellt den Typ eines Arguments, die beim Auslösen einer Ausnahme dieses Typs bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5afb2-109">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="5afb2-110">Sie können mehrere Argumente angeben, mit der ein Tupel für *Argumenttyp*.</span><span class="sxs-lookup"><span data-stu-id="5afb2-110">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="5afb2-111">Eine typische Definition für eine f#-Ausnahme sieht ungefähr so aus.</span><span class="sxs-lookup"><span data-stu-id="5afb2-111">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="5afb2-112">Sie können eine Ausnahme dieses Typs generiert, mit der `raise` -Funktion wie folgt.</span><span class="sxs-lookup"><span data-stu-id="5afb2-112">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="5afb2-113">Können Sie einen f#-Ausnahmetyp direkt in den Filtern in einem `try...with` Ausdruck, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5afb2-113">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="5afb2-114">Der Typ der Ausnahme, die Sie definieren, mit der `exception` -Schlüsselwort in f# ist eine neue Anwendungsart, die von erben `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="5afb2-114">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>


## <a name="see-also"></a><span data-ttu-id="5afb2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5afb2-115">See Also</span></span>
[<span data-ttu-id="5afb2-116">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="5afb2-116">Exception Handling</span></span>](index.md)

[<span data-ttu-id="5afb2-117">Ausnahmen: Die `raise`-Funktion</span><span class="sxs-lookup"><span data-stu-id="5afb2-117">Exceptions: the `raise` Function</span></span>](the-raise-function.md)

[<span data-ttu-id="5afb2-118">Ausnahmenhierarchie</span><span class="sxs-lookup"><span data-stu-id="5afb2-118">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)
