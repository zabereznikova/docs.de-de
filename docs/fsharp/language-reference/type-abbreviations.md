---
title: Typabkürzungen
description: Informationen Sie zu F# typabkürzungen auf einem Typ einen aussagekräftigeren Namen geben, damit der um Code leichter lesbar zu machen.
ms.date: 05/16/2016
ms.openlocfilehash: 2930db1dcaa66741900bc91937aa1fd2f006c5f8
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641685"
---
# <a name="type-abbreviations"></a><span data-ttu-id="6486b-103">Typabkürzungen</span><span class="sxs-lookup"><span data-stu-id="6486b-103">Type Abbreviations</span></span>

<span data-ttu-id="6486b-104">Ein *-typabkürzung* ist ein Alias oder alternative Namen für einen Typ.</span><span class="sxs-lookup"><span data-stu-id="6486b-104">A *type abbreviation* is an alias or alternate name for a type.</span></span>

## <a name="syntax"></a><span data-ttu-id="6486b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6486b-105">Syntax</span></span>

```fsharp
type [accessibility-modifier] type-abbreviation = type-name
```

## <a name="remarks"></a><span data-ttu-id="6486b-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6486b-106">Remarks</span></span>

<span data-ttu-id="6486b-107">Typabkürzungen können Sie einem Typ geben Sie einen aussagekräftigeren Namen, um den Code leichter lesbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="6486b-107">You can use type abbreviations to give a type a more meaningful name, in order to make code easier to read.</span></span> <span data-ttu-id="6486b-108">Sie können Sie auch verwenden, um eine benutzerfreundliche Namen für einen Typ zu erstellen, die andernfalls schwierig zu schreiben sind. Typabkürzungen können Sie darüber hinaus erleichtern es, einen zugrunde liegenden Typ ändern, ohne den Code aus, der den Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="6486b-108">You can also use them to create an easy to use name for a type that is otherwise cumbersome to write out. Additionally, you can use type abbreviations to make it easier to change an underlying type without changing all the code that uses the type.</span></span> <span data-ttu-id="6486b-109">Folgendes ist eine Abkürzung des einfachen Typs.</span><span class="sxs-lookup"><span data-stu-id="6486b-109">The following is a simple type abbreviation.</span></span>

<span data-ttu-id="6486b-110">Zugriff auf typabkürzungen standardmäßig `public`.</span><span class="sxs-lookup"><span data-stu-id="6486b-110">Accessibility of type abbreviations defaults to `public`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2301.fs)]

<span data-ttu-id="6486b-111">Typabkürzungen können es sich um generische Parameter, wie im folgenden Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="6486b-111">Type abbreviations can include generic parameters, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2302.fs)]

<span data-ttu-id="6486b-112">Im vorherigen Code `Transform` ist eine typabkürzung, die eine Funktion darstellt, die ein einzelnes Argument eines beliebigen Typs akzeptiert und einen einzelnen Wert desselben Typs zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6486b-112">In the previous code, `Transform` is a type abbreviation that represents a function that takes a single argument of any type and that returns a single value of that same type.</span></span>

<span data-ttu-id="6486b-113">Typabkürzungen werden nicht in der .NET Framework-MSIL-Code beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6486b-113">Type abbreviations are not preserved in the .NET Framework MSIL code.</span></span> <span data-ttu-id="6486b-114">Aus diesem Grund bei Verwendung einer F# Assembly von einer anderen .NET Framework-Sprache, müssen Sie den zugrunde liegenden Typnamen für eine typabkürzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="6486b-114">Therefore, when you use an F# assembly from another .NET Framework language, you must use the underlying type name for a type abbreviation.</span></span>

<span data-ttu-id="6486b-115">Typabkürzungen können auch auf Maßeinheiten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6486b-115">Type abbreviations can also be used on units of measure.</span></span> <span data-ttu-id="6486b-116">Weitere Informationen finden Sie unter [Einheiten](units-of-measure.md).</span><span class="sxs-lookup"><span data-stu-id="6486b-116">For more information, see [Units of Measure](units-of-measure.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6486b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6486b-117">See also</span></span>

- [<span data-ttu-id="6486b-118">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="6486b-118">F# Language Reference</span></span>](index.md)
