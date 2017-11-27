---
title: "Typabkürzungen (F#)"
description: "Informationen Sie zu f# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, um den Code verständlicher zu gestalten."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 560af74f-935f-415c-af56-604cddb9da6b
ms.openlocfilehash: 235c0240fe89d203b9474dec2b3f91947f453cd8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="type-abbreviations"></a><span data-ttu-id="9759c-104">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="9759c-104">Type Abbreviations</span></span>

<span data-ttu-id="9759c-105">Ein *-typabkürzung* einen Alias oder ein alternativer Name für einen Typ ist.</span><span class="sxs-lookup"><span data-stu-id="9759c-105">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="9759c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9759c-106">Syntax</span></span>

```fsharp
type type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="9759c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9759c-107">Remarks</span></span>
<span data-ttu-id="9759c-108">Typabkürzungen können Sie einem Typ einen aussagekräftigeren Namen geben, um den Code verständlicher zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="9759c-108">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="9759c-109">Sie können Sie auch verwenden, um eine einfach zu verwendende Name für einen Typ zu erstellen, die andernfalls schwierig zu schreiben sind. Darüber hinaus können Sie typabkürzungen verwenden, um ihn leichter ändern, einen zugrunde liegenden Typ ohne Ändern der gesamte Code, der den Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="9759c-109">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="9759c-110">Der folgende Code ist eine Abkürzung des einfachen Typs.</span><span class="sxs-lookup"><span data-stu-id="9759c-110">The following is a simple type abbreviation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="9759c-111">Typabkürzungen zählen generische Parameter, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="9759c-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="9759c-112">Im vorherigen Code `Transform` ist eine typabkürzung, der eine Funktion darstellt, die ein einzelnes eines beliebigen Typs Argument und einen einzelnen Wert desselben Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="9759c-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="9759c-113">Typabkürzungen werden in der .NET Framework-MSIL-Code nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="9759c-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="9759c-114">Bei Verwendung eine f#-Assembly aus einer anderen .NET Framework-Sprache müssen Sie daher der Typname des zugrunde liegenden für typabkürzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="9759c-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="9759c-115">Typabkürzungen können auch für Maßeinheiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9759c-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="9759c-116">Weitere Informationen finden Sie unter [Einheiten](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="9759c-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="9759c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9759c-117">See Also</span></span>
[<span data-ttu-id="9759c-118">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="9759c-118">F# Language Reference</span></span>](index.md)

