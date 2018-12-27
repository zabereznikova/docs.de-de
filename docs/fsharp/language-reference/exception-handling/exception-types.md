---
title: Ausnahmetypen
description: Erfahren Sie, wie Sie definieren und Verwenden von F# Ausnahmetypen.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612828"
---
# <a name="exception-types"></a><span data-ttu-id="e75ca-103">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="e75ca-103">Exception Types</span></span>

<span data-ttu-id="e75ca-104">Es gibt zwei Kategorien von Ausnahmen in F#: Ausnahmetypen in .NET und F#-Typen.</span><span class="sxs-lookup"><span data-stu-id="e75ca-104">There are two categories of exceptions in F#: .NET exception types and F# exception types.</span></span> <span data-ttu-id="e75ca-105">In diesem Thema wird beschrieben, wie Sie definieren und verwenden F# Ausnahmetypen.</span><span class="sxs-lookup"><span data-stu-id="e75ca-105">This topic describes how to define and use F# exception types.</span></span>

## <a name="syntax"></a><span data-ttu-id="e75ca-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e75ca-106">Syntax</span></span>

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a><span data-ttu-id="e75ca-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e75ca-107">Remarks</span></span>

<span data-ttu-id="e75ca-108">In der vorherigen Syntax *Ausnahmetyp* ist der Name eines neuen F# Ausnahmetyp und *Argumenttyp* stellt den Typ eines Arguments, die beim Auslösen einer Ausnahme dieses Typs bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e75ca-108">In the previous syntax, *exception-type* is the name of a new F# exception type, and *argument-type* represents the type of an argument that can be supplied when you raise an exception of this type.</span></span> <span data-ttu-id="e75ca-109">Sie können mehrere Argumente angeben, indem Sie verwenden einen Tupeltyp für *Argumenttyp*.</span><span class="sxs-lookup"><span data-stu-id="e75ca-109">You can specify multiple arguments by using a tuple type for *argument-type*.</span></span>

<span data-ttu-id="e75ca-110">Eine typische Definition für eine F# Ausnahme der folgenden Darstellung ähnelt.</span><span class="sxs-lookup"><span data-stu-id="e75ca-110">A typical definition for an F# exception resembles the following.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

<span data-ttu-id="e75ca-111">Sie können eine Ausnahme dieses Typs generieren, mit der `raise` -Funktion wie folgt.</span><span class="sxs-lookup"><span data-stu-id="e75ca-111">You can generate an exception of this type by using the `raise` function, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

<span data-ttu-id="e75ca-112">Können Sie eine F# Ausnahmetyp direkt in die Filter in einem `try...with` Ausdruck wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e75ca-112">You can use an F# exception type directly in the filters in a `try...with` expression, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

<span data-ttu-id="e75ca-113">Der Typ der Ausnahme, die Sie definieren, mit der `exception` Schlüsselwort in F# ist eine neue Art, die von erbt `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="e75ca-113">The exception type that you define with the `exception` keyword in F# is a new type that inherits from `System.Exception`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e75ca-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e75ca-114">See also</span></span>

- [<span data-ttu-id="e75ca-115">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="e75ca-115">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="e75ca-116">Ausnahmen: Die `raise`-Funktion</span><span class="sxs-lookup"><span data-stu-id="e75ca-116">Exceptions: the `raise` Function</span></span>](the-raise-function.md)
- [<span data-ttu-id="e75ca-117">Ausnahmenhierarchie</span><span class="sxs-lookup"><span data-stu-id="e75ca-117">Exception Hierarchy</span></span>](https://msdn.microsoft.com/library/z4c5tckx.aspx)