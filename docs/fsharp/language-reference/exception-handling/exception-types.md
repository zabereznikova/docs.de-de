---
title: Ausnahmetypen
description: 'Erfahren Sie, wie Sie F #-Ausnahme Typen definieren und verwenden.'
ms.date: 05/16/2016
ms.openlocfilehash: 8b4ceec31a2d68abbcd025812ffeeefc0c090efb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557228"
---
# <a name="exception-types"></a><span data-ttu-id="f23b2-103">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="f23b2-103">Exception Types</span></span>

<span data-ttu-id="f23b2-104">Es gibt zwei Kategorien von Ausnahmen in f #: .NET-Ausnahme Typen und f #-Ausnahme Typen.</span><span class="sxs-lookup"><span data-stu-id="f23b2-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="f23b2-105">In diesem Thema wird beschrieben, wie Sie F #-Ausnahme Typen definieren und verwenden.</span><span class="sxs-lookup"><span data-stu-id="f23b2-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="f23b2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f23b2-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="f23b2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f23b2-107">Remarks</span></span>

<span data-ttu-id="f23b2-108">In der vorherigen Syntax ist *Exception-Type* der Name eines neuen F #-Ausnahme Typs, und der *Argumenttyp* stellt den Typ eines Arguments dar, das bereitgestellt werden kann, wenn Sie eine Ausnahme dieses Typs auslöst.</span><span class="sxs-lookup"><span data-stu-id="f23b2-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="f23b2-109">Sie können mehrere Argumente angeben, indem Sie einen tupeltyp für den *Argumenttyp*verwenden.</span><span class="sxs-lookup"><span data-stu-id="f23b2-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="f23b2-110">Eine typische Definition für eine F #-Ausnahme ähnelt der folgenden.</span><span class="sxs-lookup"><span data-stu-id="f23b2-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="f23b2-111">Sie können eine Ausnahme dieses Typs generieren, indem Sie die- `raise` Funktion wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="f23b2-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="f23b2-112">Sie können einen F #-Ausnahmetyp direkt in den Filtern in einem- `try...with` Ausdruck verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f23b2-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="f23b2-113">Der Ausnahmetyp, den Sie mit dem- `exception` Schlüsselwort in F # definieren, ist ein neuer Typ, der von erbt `System.Exception` .</span><span class="sxs-lookup"><span data-stu-id="f23b2-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f23b2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f23b2-114">See also</span></span>

- [<span data-ttu-id="f23b2-115">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="f23b2-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="f23b2-116">Ausnahmen: Die `raise`-Funktion</span><span class="sxs-lookup"><span data-stu-id="f23b2-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="f23b2-117">Ausnahmenhierarchie</span><span class="sxs-lookup"><span data-stu-id="f23b2-117">Exception Hierarchy</span></span>](../../../standard/exceptions/index.md)
